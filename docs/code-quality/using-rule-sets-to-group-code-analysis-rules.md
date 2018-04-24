---
title: 在 Visual Studio 中的代码分析规则集
ms.date: 04/02/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.rulesets.learnmore
helpviewer_keywords:
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3a445aecdd5a9f02bca8d43e42646c991742a626
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="use-rule-sets-to-group-code-analysis-rules"></a>使用规则集组合代码分析规则

在 Visual Studio 中配置代码分析时，你可以从内置的列表中选择*规则集*。 规则集适用于一个项目，并且是用于标识目标的问题和为该项目的特定条件分析规则的代码的分组。 例如，你可以应用一种旨在扫描公开可用 Api 代码的规则集，或只需最少量建议规则。 你还可以应用包含所有规则的规则集。

你可以自定义规则集通过添加或删除规则，或者通过更改规则严重级别以显示为警告或中的错误**错误列表**。 自定义的规则集可以满足为特定的开发环境的需要。 自定义规则集时，规则集编辑器提供搜索和筛选工具来帮助你在过程中。

## <a name="rule-set-format"></a>规则将格式设置

中的 XML 格式指定规则集 *.ruleset*文件。 包含 ID 的规则和*操作*，按分析器 ID 和文件中的命名空间进行分组。

XML 内容 *.ruleset*文件类似于以下：

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
> 这样便很容易[编辑规则集](../code-quality/working-in-the-code-analysis-rule-set-editor.md)中的图形**规则集编辑器**比手动。

规则集为项目指定通过`CodeAnalysisRuleSet`Visual Studio 项目文件中的属性。 例如：

```xml
<CodeAnalysisRuleSet>HelloWorld.ruleset</CodeAnalysisRuleSet>
```

## <a name="see-also"></a>请参阅

- [代码分析规则集参考](../code-quality/rule-set-reference.md)
