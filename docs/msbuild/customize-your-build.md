---
title: "自定义生成 | Microsoft Docs"
ms.custom: 
ms.date: 06/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, transforms
- transforms [MSBuild]
ms.assetid: d0bceb3b-14fb-455c-805a-63acefa4b3ed
caps.latest.revision: "13"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 9392776d44602ee81358e31708d331e09d0d7a70
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="customize-your-build"></a>自定义生成
在 MSBuild 15 版之前的版本中，如果要向解决方案中的项目提供新的自定义属性，必须手动向解决方案中的每个项目文件添加一个针对该属性的引用。 另外，还必须在 .props 文件中定义属性，在解决方案的每个项目中显式导入该 .props 文件。

但现在通过在存储库根目录下名为 Directory.Build.props 的单个文件中定义一个新属性，只需一步即可向每个项目添加该属性。 MSBuild 运行时，Microsoft.Common.props 会搜索 Directory.Build.props 文件的目录结构（Microsoft.Common.targets 将查找 Directory.Build.targets）。 如果找到，就会导入该属性。 Directory.Build.props 是用户定义文件，对目录下的项目提供自定义选项。

## <a name="directorybuildprops-example"></a>Directory.Build.props 示例
例如，如果想要使所有项目都可以访问新的 Roslyn /deterministic 功能（属性 `$(Deterministic)` 在 Roslyn CoreCompile 目标中公开了此功能），可以执行以下操作。

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

## <a name="search-scope"></a>搜索范围
搜索 Directory.Build.props 文件时，MSBuild 将从项目位置 ($(MSBuildProjectFullPath)) 向上搜索目录结构，找到 Directory.Build.props 文件后停止。 例如，如果 $(MSBuildProjectFullPath) 为 c:\users\username\code\test\case1，MSBuild 将从该位置开始搜索，然后向上搜索目录结构，直到找到 Directory.Build.props 文件，如以下目录结构中所示。

```
c:\users\username\code\test\case1
c:\users\username\code\test
c:\users\username\code
c:\users\username
c:\users
c:\
```
解决方案文件的位置与 Directory.Build.props 无关。

## <a name="import-order"></a>导入顺序

Directory.Build.props 很早便已导入 Microsoft.Common.props，因此它无法使用后来定义的属性。 因此，请避免引用尚未定义的属性（否则计算结果将为空）。

从 NuGet 包导入 .targets 文件后，会从 Microsoft.Common.targets 导入 Directory.Build.targets。 因此，可使用它替代在大部分生成逻辑中定义的属性和目标，但有时可能必须在最终导入后在项目文件内进行自定义。

## <a name="use-case-multi-level-merging"></a>用例：多级别合并

假设你具有此标准解决方案结构：

````
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
````

则可能需要具有所有项目 `(1)` 的通用属性、`src` 项目 `(2-src)` 的通用属性，以及 `test` 项目 `(2-test)` 的通用属性。

为了 msbuild 正确地合并“内部”文件（`2-src` 和 `2-test`）和“外部”文件 (`1`)，必须考虑到 msbuild 找到 `Directory.Build.props` 文件后会立即停止进一步的扫描。 要继续扫描并合并到外部文件，请将此置于这两个内部文件中：

`<Import Project="$([MSBuild]::GetPathOfFileAbove('Directory.Build.props', '$(MSBuildThisFileDirectory)../'))" />`

msbuild 的常规方法的摘要如下所示：

- 对于任何给定的项目，msbuild 在解决方案结构中向上查找第一个 `Directory.Build.props`，将其与默认项合并，然后停止扫描
- 如果要找到并合并多个级别，则从“内部”文件 [`<Import...>`](http://docs.microsoft.com/en-us/visualstudio/msbuild/property-functions#msbuild-getpathoffileabove)（如上所示）“外部”文件
- 如果“外部”文件本身不会再导入其上的内容，则扫描在此处停止
- 要控制扫描/合并过程，请使用 `$(DirectoryBuildPropsPath)` 和 `$(ImportDirectoryBuildProps)`

或再简单点：不能导入任何内容的第一个 `Directory.Build.props` 即为 msbuild 停止的位置。

## <a name="see-also"></a>另请参阅  
 [MSBuild 概念](../msbuild/msbuild-concepts.md)   
 [MSBuild 参考](../msbuild/msbuild-reference.md)   
