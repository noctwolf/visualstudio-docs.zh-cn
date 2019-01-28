---
title: 代码分析规则集
ms.date: 04/02/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.rulesets.learnmore
helpviewer_keywords:
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4095ee54dd724056ad976f0be2591113337a5341
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55009652"
---
# <a name="use-rule-sets-to-group-code-analysis-rules"></a>使用规则集对代码分析规则进行分组

在 Visual Studio 中配置代码分析时，可以从内置列表中选择*规则集*。 规则集应用于一个项目，并且是确定目标的问题和对该项目的特定条件的分析规则的代码的分组。 例如，可以应用旨在扫描公开可用 Api 代码的规则集，或只需最少量建议规则。 您还可以应用一个规则集，包括所有规则。

你可以自定义规则集通过添加或删除规则，或更改规则的严重级别显示为警告性警报或中的错误**错误列表**。 自定义的规则集可满足特定的开发环境的需求。 自定义规则集时，规则集编辑器提供了搜索和筛选工具来帮助您在过程中。

规则集是可用于[托管代码的静态分析](how-to-configure-code-analysis-for-a-managed-code-project.md)， [c + + 代码分析](using-rule-sets-to-specify-the-cpp-rules-to-run.md)，并[Roslyn 分析器](analyzer-rule-sets.md)。

## <a name="rule-set-format"></a>规则将格式设置

规则集指定中的 XML 格式 *.ruleset*文件。 规则包含一个 ID 和一个*操作*，按分析器 ID 和文件中的命名空间进行分组。

内容 *.ruleset*文件看起来类似于此 XML:

```xml
<RuleSet Name="Rules for Hello World project" Description="These rules focus on critical issues for the Hello World app." ToolsVersion="10.0">
  <Localization ResourceAssembly="Microsoft.VisualStudio.CodeAnalysis.RuleSets.Strings.dll" ResourceBaseName="Microsoft.VisualStudio.CodeAnalysis.RuleSets.Strings.Localized">
    <Name Resource="HelloWorldRules_Name" />
    <Description Resource="HelloWorldRules_Description" />
  </Localization>
  <Rules AnalyzerId="Microsoft.Analyzers.ManagedCodeAnalysis" RuleNamespace="Microsoft.Rules.Managed">
    <Rule Id="CA1001" Action="Warning" />
    <Rule Id="CA1009" Action="Warning" />
    <Rule Id="CA1016" Action="Warning" />
    <Rule Id="CA1033" Action="Warning" />
  </Rules>
  <Rules AnalyzerId="Microsoft.CodeQuality.Analyzers" RuleNamespace="Microsoft.CodeQuality.Analyzers">
    <Rule Id="CA1802" Action="Error" />
    <Rule Id="CA1814" Action="Info" />
    <Rule Id="CA1823" Action="None" />
    <Rule Id="CA2217" Action="Warning" />
  </Rules>
</RuleSet>
```

> [!TIP]
> 更轻松地[编辑规则集](../code-quality/working-in-the-code-analysis-rule-set-editor.md)中的图形**规则集编辑器**比手动。

## <a name="specify-a-rule-set-for-a-project"></a>指定为项目设置的规则

规则集为项目指定由**CodeAnalysisRuleSet** Visual Studio 项目文件中的属性。 例如：

```xml
<PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
  ...
  <CodeAnalysisRuleSet>HelloWorld.ruleset</CodeAnalysisRuleSet>
</PropertyGroup>
```

## <a name="see-also"></a>请参阅

- [代码分析规则集参考](../code-quality/rule-set-reference.md)