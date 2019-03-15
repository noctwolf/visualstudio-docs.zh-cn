---
title: 配置使用 editorconfig FxCop 分析器
ms.date: 03/11/2019
ms.topic: conceptual
helpviewer_keywords:
- FxCop analyzers, configuring
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ac751b7ec130b6bfbb18752c02b491b6c342f172
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57874660"
---
# <a name="configure-fxcop-analyzers"></a>配置 FxCop 分析器

[FxCop 分析器](install-fxcop-analyzers.md)包含静态代码分析，转换为 Roslyn 分析器中的最重要"FxCop"规则。 可以通过两种方式来配置 FxCop 代码分析器：

- 与[规则集](#fxcop-analyzer-rule-sets)，它可让你启用或禁用规则并设置单个规则冲突的严重性。

- 从版本 2.6.3 [Microsoft.CodeAnalysis.FxCopAnalyzers](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers) NuGet 包，通过[.editorconfig 文件](#editorconfig-file)。 [可配置选项](fxcop-analyzer-options.md)优化的哪些部分可让您基本代码，以分析。

> [!TIP]
> FxCop 静态代码分析和 FxCop 分析器之间差异的信息，请参阅[FxCop 分析器常见问题解答](fxcop-analyzers-faq.md)。

## <a name="fxcop-analyzer-rule-sets"></a>FxCop 分析器规则集

若要配置 FxCop 分析器的一种方法是使用 XML*规则集*。 规则集是确定目标的问题和特定条件的代码分析规则的分组。 规则集，可以启用或禁用规则并设置单个规则冲突的严重性。

FxCop 分析器 NuGet 包包含以下规则类别的预定义的规则集：

- 设计
- 文档
- 可维护性
- 命名
- 性能
- 可靠性
- 安全性
- 用法

有关详细信息，请参阅[规则集适用于 Roslyn 分析器](analyzer-rule-sets.md)。

## <a name="editorconfig-file"></a>EditorConfig 文件

可以通过添加到的键 / 值对配置分析程序规则[.editorconfig](https://editorconfig.org)文件。 配置文件可以是[特定于项目](#per-project-configuration)也可以是[共享](#shared-configuration)两个或多个项目之间。

### <a name="per-project-configuration"></a>每个项目配置

若要启用基于.editorconfig 的分析器针对某个特定项目的配置，请添加 *.editorconfig*项目的根目录的文件。

> [!TIP]
> 您可以通过右键单击该项目中添加到你的项目.editorconfig 文件**解决方案资源管理器**，然后选择**添加** > **新项**。 在中**添加新项**窗口中，输入**editorconfig**在搜索框中。 选择**editorconfig 文件 （默认值）** 模板，然后选择**添加**。
>
> ![将 editorconfig 项添加到 Visual Studio 中的项目](media/add-editorconfig-file.png)

当前没有层次结构支持对"组合".editorconfig 的文件的存在于不同的目录级别，例如，解决方案和项目级别。

### <a name="shared-configuration"></a>共享的配置

可以共享分析器配置两个或多个项目之间的.editorconfig 文件，但需要一些额外的步骤。

1. 保存 *.editorconfig*到常见位置的文件。

2. 创建 *.props*文件包含以下内容：

   ```xml
   <Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
     <PropertyGroup>
       <SkipDefaultEditorConfigAsAdditionalFile>true</SkipDefaultEditorConfigAsAdditionalFile>
     </PropertyGroup>
     <ItemGroup Condition="Exists('<your path>\.editorconfig')" >
       <AdditionalFiles Include="<your path>\.editorconfig" />
     </ItemGroup>
   </Project>
   ```

3. 将行添加到您 *.csproj*或 *.vbproj*要导入文件 *.props*在上一步中创建的文件。 必须在导入的 FxCop 分析器任何行之前放置此行 *.props*文件。 例如，如果名为.props 文件*editorconfig.props*:

   ```xml
   ...
   <Import Project="..\..\editorconfig.props" Condition="Exists('..\..\editorconfig.props')" />
   <Import Project="..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.3\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props" Condition="Exists('..\packages\Microsoft.CodeAnalysis.FxCopAnalyzers.2.6.3\build\Microsoft.CodeAnalysis.FxCopAnalyzers.props')" />
   ...
   ```

4. 重新加载项目。

> [!NOTE]
> 不能使用.editorconfig 文件来配置旧的 FxCop 规则 （静态代码分析 FxCop）。

## <a name="option-scopes"></a>作用域选项

所有规则、 类别的规则 （例如，命名或设计） 或特定的规则，可以配置每个选项。

### <a name="all-rules"></a>所有规则

配置所有规则的选项的语法如下所示：

|语法|示例|
|-|-|
| dotnet_code_quality.OptionName = OptionValue | `dotnet_code_quality.api_surface = public` |

### <a name="category-of-rules"></a>类别的规则

配置选项的语法*类别*的 （如命名、 设计或性能） 的规则如下所示：

|语法|示例|
|-|-|
| dotnet_code_quality.RuleCategory.OptionName = OptionValue | `dotnet_code_quality.Naming.api_surface = public` |

### <a name="specific-rule"></a>特定的规则

配置适用于特定规则选项的语法如下所示：

|语法|示例|
|-|-|
| dotnet_code_quality.RuleId.OptionName = OptionValue | `dotnet_code_quality.CA1040.api_surface = public` |

## <a name="see-also"></a>请参阅

- [分析器的配置](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md)
- [FxCop 分析器](install-fxcop-analyzers.md)
