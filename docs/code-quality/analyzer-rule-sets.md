---
title: 分析器规则集
ms.date: 07/20/2018
ms.topic: conceptual
helpviewer_keywords:
- analyzers, rule sets
- rule sets for analyzers
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 567d315694ff4f55ae5e1d2df2e7963bc21902a3
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55932009"
---
# <a name="rule-sets-for-roslyn-analyzers"></a>规则集适用于 Roslyn 分析器

一些 NuGet 分析器包包含预定义的规则集。 例如，规则集附带[Microsoft.CodeAnalysis.FxCopAnalyzers NuGet 分析器包](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/)（从版本 2.6.2） 启用或禁用规则根据其类别，例如安全性，命名，或性能。 使用规则集，可以轻松地快速查看仅与特定类别的规则相关的这些规则冲突。

如果要从旧版"FxCop"静态代码分析迁移到 Roslyn 分析器，这些规则集，可继续使用前面用过的相同规则配置。

## <a name="use-analyzer-rule-sets"></a>使用分析工具规则集

之后您[安装 NuGet 分析器包](install-roslyn-analyzers.md)，找到预定义的规则中设置其*ruleset*目录，例如 *%USERPROFILE%\\.nuget\packages\microsoft.codequality.analyzers\<版本 > \rulesets*。 在这里，可以拖动和删除，请复制并粘贴一个或多个到 Visual Studio 项目中的 ruleset**解决方案资源管理器**。

若要使规则集的活动规则集进行分析，右键单击该项目中**解决方案资源管理器**，然后选择**属性**。 在项目属性页中，选择**代码分析**选项卡。下**运行此规则集**，选择**浏览**，然后选择所需的规则集复制到项目目录。 现在您只看到在所选的规则集中启用这些规则的规则冲突。

此外可以[自定义预定义的规则集](how-to-create-a-custom-rule-set.md#create-a-custom-rule-set)到您的首选项。 例如，可以更改一个或多个规则的严重性，以便为错误或警告中的会显示冲突**错误列表**。

## <a name="available-rule-sets"></a>可用的规则集

预定义的分析器规则集包括三个会影响包中的所有规则的规则集&mdash;一个，使其全部、 禁用所有这些模板，其中一个，另一个遵循每个规则的默认的严重性和启用设置：

- AllRulesEnabled.ruleset
- AllRulesDisabled.ruleset
- AllRulesDefault.ruleset

此外，还有针对每个类别中的包，如性能或安全规则的两个规则集。 一个规则集启用所有规则的类别，并将一个规则集尊重类别中每个规则的默认严重性和启用设置。

 [Microsoft.CodeAnalysis.FxCopAnalyzers NuGet 分析器包](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/)包括以下类别，以匹配用于旧"FxCop"静态代码分析规则集的规则集：

- 设计
- 文档
- 可维护性
- 命名
- 性能
- 可靠性
- 安全性
- 用法

## <a name="see-also"></a>请参阅

- [.NET Compiler Platform 分析器概述](roslyn-analyzers-overview.md)
- [安装.NET Compiler Platform 分析器](install-roslyn-analyzers.md)
- [配置和使用 Roslyn 分析程序规则](use-roslyn-analyzers.md)
- [使用规则集对代码分析规则进行分组](using-rule-sets-to-group-code-analysis-rules.md)