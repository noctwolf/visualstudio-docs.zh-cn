---
title: 自定义生成 | Microsoft Docs
ms.date: 06/14/2017
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, transforms
- transforms [MSBuild]
ms.assetid: d0bceb3b-14fb-455c-805a-63acefa4b3ed
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fc4515ad8f61d749c9fb7552911bfb15dcc3471a
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56610328"
---
# <a name="customize-your-build-c-visual-basic"></a>自定义生成（C#，Visual Basic）

使用标准生成进程（导入 Microsoft.Common.props 和 Microsoft.Common.targets）的 MSBuild 项目有多个可用于自定义生成过程的扩展性挂钩。

## <a name="add-arguments-to-command-line-msbuild-invocations-for-your-project"></a>向项目的命令行 MSBuild 调用添加参数

源目录中或之上的 Directory.Build.rsp 文件将应用到项目的命令行生成。 有关详细信息，请参阅 [MSBuild 响应文件](../msbuild/msbuild-response-files.md#directorybuildrsp)。

## <a name="directorybuildprops-and-directorybuildtargets"></a>Directory.Build.props 和 Directory.Build.targets

在 MSBuild 15 版之前，如果要向解决方案中的项目提供新的自定义属性，必须手动向解决方案中的每个项目文件添加一个针对该属性的引用。 另外，还必须在 .props 文件中定义属性，然后在解决方案的每个项目中显式导入该 .props 文件。

但现在，通过在包含源的根文件夹的名为 Directory.Build.props 的单个文件中定义一个新属性，只需一步即可向每个项目添加该属性。 在 MSBuild 运行时，Microsoft.Common.props 会搜索 Directory.Build.props 文件的目录结构（Microsoft.Common.targets 将查找 Directory.Build.targets）。 如果找到，就会导入该属性。 Directory.Build.props 是用户定义文件，对目录下的项目提供自定义选项。

> [!NOTE]
> 基于 Linux 的文件系统区分大小写。 请确保 Directory.Build.props 文件名的大小写完全匹配，否则将不会在生成流程中检测到它。
>
> 有关详细信息，请参阅[此 GitHub 问题](https://github.com/dotnet/core/issues/1991#issue-368441031)。

### <a name="directorybuildprops-example"></a>Directory.Build.props 示例

例如，如果想要使所有项目都可以访问新的 Roslyn /deterministic 功能（属性 `$(Deterministic)` 在 Roslyn `CoreCompile` 目标中公开了此功能），可以执行以下操作。

1. 在存储库根目录中创建一个名为 Directory.Build.props 的新文件。
2. 将以下 XML 添加到此文件。

   ```xml
   <Project>
    <PropertyGroup>
      <Deterministic>true</Deterministic>
    </PropertyGroup>
   </Project>
   ```
3. 运行 MSBuild。 项目现有的 Microsoft.Common.props 和 Microsoft.Common.targets 导入会找到该文件并将其导入。

### <a name="search-scope"></a>搜索范围

搜索 Directory.Build.props 文件时，MSBuild 将从项目位置 (`$(MSBuildProjectFullPath)`) 向上搜索目录结构，找到 Directory.Build.props 文件后停止。 例如，如果 `$(MSBuildProjectFullPath)` 为 c:\users\username\code\test\case1，MSBuild 将从该位置开始搜索，然后向上搜索目录结构，直到找到 Directory.Build.props 文件，如以下目录结构中所示。

```
c:\users\username\code\test\case1
c:\users\username\code\test
c:\users\username\code
c:\users\username
c:\users
c:\
```

解决方案文件的位置与 Directory.Build.props 无关。

### <a name="import-order"></a>导入顺序

Directory.Build.props 很早便已导入 Microsoft.Common.props，因此它无法使用后来定义的属性。 因此，请避免引用尚未定义的属性（否则计算结果将为空）。

从 NuGet 包导入 .targets 文件后，会从 Microsoft.Common.targets 导入 Directory.Build.targets。 因此，它会重写大部分生成逻辑中定义的属性和目标，但有时候，可能需要在最终导入后自定义项目文件。

### <a name="use-case-multi-level-merging"></a>用例：多级别合并

假设你具有此标准解决方案结构：

```
\
  MySolution.sln
  Directory.Build.props     (1)
  \src
    Directory.Build.props   (2-src)
    \Project1
    \Project2
  \test
    Directory.Build.props   (2-test)
    \Project1Tests
    \Project2Tests
```

则可能需要具有所有项目 (1) 的通用属性、src 项目 (2-src) 的通用属性，以及 test 项目 (2-test) 的通用属性。

若要 MSBuild 正确地合并“内部”文件（2-src 和 2-test）和“外部”文件 (1)，必须考虑到 MSBuild 找到 Directory.Build.props 文件后会立即停止进一步的扫描。 要继续扫描并合并到外部文件，请将此代码置于这两个内部文件中：

`<Import Project="$([MSBuild]::GetPathOfFileAbove('Directory.Build.props', '$(MSBuildThisFileDirectory)../'))" />`

MSBuild 的常规方法汇总如下：

- 对于任何给定的项目，MSBuild 在解决方案结构中向上查找第一个 Directory.Build.props，将其与默认项合并，然后停止扫描
- 如果要找到并合并多个级别，则从“内部”文件 [`<Import...>`](../msbuild/property-functions.md#msbuild-getpathoffileabove)（如上所示）“外部”文件
- 如果“外部”文件本身不会再导入其上的内容，则扫描在此处停止
- 要控制扫描/合并过程，请使用 `$(DirectoryBuildPropsPath)` 和 `$(ImportDirectoryBuildProps)`

或再简单点：不能导入任何内容的第一个 Directory.Build.props 即为 MSBuild 停止的位置。

## <a name="msbuildprojectextensionspath"></a>MSBuildProjectExtensionsPath

默认情况下，Microsoft.Common.props 导入 `$(MSBuildProjectExtensionsPath)$(MSBuildProjectFile).*.props`，Microsoft.Common.targets 导入 `$(MSBuildProjectExtensionsPath)$(MSBuildProjectFile).*.targets`。 `MSBuildProjectExtensionsPath` 的默认值是 `$(BaseIntermediateOutputPath)`、`obj/`。 NuGet 用此机制来引用随包提供的生成逻辑，也就是说，在还原时，它会创建引用包内容的 `{project}.nuget.g.props` 文件。

可以通过在 Directory.Build.props 中或者在导入 Microsoft.Common.props 前将属性 `ImportProjectExtensionProps` 设为 `false` 来禁用此扩展性机制。

> [!NOTE]
> 禁用 MSBuildProjectExtensionsPath 导入将阻止在 NuGet 包中提供的生成逻辑应用到你的项目。 一些 NuGet 包需要生成逻辑来执行其功能，并且在禁用该功能时会呈现不可用。

## <a name="user-file"></a>.user 文件

Microsoft.Common.CurrentVersion.targets 会导入 `$(MSBuildProjectFullPath).user`（如果存在），因此可以使用其他文件扩展名在你的项目旁创建一个文件。 对于计划签入源代码管理的长期更改，最好更改项目本身，以便将来的维护人员不必了解此扩展机制。

## <a name="msbuildextensionspath-and-msbuilduserextensionspath"></a>MSBuildExtensionsPath 和 MSBuildUserExtensionsPath

> [!WARNING]
> 如果使用这些扩展机制，则较难获取计算机上的可重复生成。 尝试使用可以签入源代码管理系统并在基本代码的所有开发人员之间共享的配置。

按照惯例，许多核心生成逻辑文件

```xml
$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\{TargetFileName}\ImportBefore\*.targets
```

会在其内容前后各导入一次

```xml
$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\{TargetFileName}\ImportAfter\*.targets
```

。 这使已安装的 SDK 可以增强常见项目类型的生成逻辑。

在 `$(MSBuildUserExtensionsPath)` 中搜索相同的目录结构，即按用户文件夹 %LOCALAPPDATA%\Microsoft\MSBuild。 放置在该文件夹中的文件将被导入该用户凭据下运行的相应项目类型的所有生成。 通过在模式 `ImportUserLocationsByWildcardBefore{ImportingFileNameWithNoDots}` 中设置以导入文件命名的属性，可以禁用用户扩展。 例如，将 `ImportUserLocationsByWildcardBeforeMicrosoftCommonProps` 设置为 `false` 会阻止导入 `$(MSBuildUserExtensionsPath)\$(MSBuildToolsVersion)\Imports\Microsoft.Common.props\ImportBefore\*`。

## <a name="customize-the-solution-build"></a>自定义解决方案生成

> [!IMPORTANT]
> 以这种方式自定义解决方案生成将仅适用于带有 MSBuild.exe 的命令行生成。 它不适用于 Visual Studio 中的生成。

当 MSBuild 生成解决方案文件时，它首先在内部转换为项目文件，然后再生成它。 已生成的项目文件在定义任何目标前导入 `before.{solutionname}.sln.targets`，在导入目标后导入 `after.{solutionname}.sln.targets` ，其中包括安装到 `$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\SolutionFile\ImportBefore` 和 `$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\SolutionFile\ImportAfter` 目录的目标。

例如，可以在包含以下内容的名为 after.MyCustomizedSolution.sln.targets 的相同目录中创建文件，从而定义在生成 MyCustomizedSolution.sln 后写自定义日志消息的新目标

```xml
<Project>
 <Target Name="EmitCustomMessage" AfterTargets="Build">
   <Message Importance="High" Text="The solution has completed the Build target" />
 </Target>
</Project>
```

## <a name="see-also"></a>请参阅

- [MSBuild 概念](../msbuild/msbuild-concepts.md)

- [MSBuild 参考](../msbuild/msbuild-reference.md)
