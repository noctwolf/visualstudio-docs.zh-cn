---
title: 使用规则集对代码分析规则进行分组 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.codeanalysis.rulesets.learnmore
helpviewer_keywords:
- code analysis, rule sets
ms.assetid: ed0f3a2a-1516-42e2-92de-b8986dc75d42
caps.latest.revision: 38
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ae7374ae6b713fe7fa1911cdcce3effa600482b1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483473"
---
# <a name="using-rule-sets-to-group-code-analysis-rules"></a>使用规则集对代码分析规则进行分组
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[使用规则集组合代码分析规则](https://docs.microsoft.com/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules)。  
  
当配置中的代码分析[!INCLUDE[vsUltLong](../includes/vsultlong-md.md)]， [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)]，或[!INCLUDE[vsPro](../includes/vspro-md.md)]，你可以从 Microsoft 内置列表中选择*规则集*。 规则集是确定目标的问题和特定条件的代码分析规则的逻辑分组。 例如，可以应用旨在扫描公开可用 Api 代码的规则集，也可以应用包含最少量建议规则的规则集。 您还可以应用一个规则集，包括所有规则。  
  
 你可以自定义规则集通过添加或删除规则，或更改规则中出现**错误列表**为警告或错误窗口。 自定义的规则集可满足特定的开发环境的需求。 自定义规则集时，规则的设置页提供了搜索和筛选工具来帮助您在过程中。  
  
## <a name="common-tasks"></a>常规任务  
  
|任务|相关内容|  
|----------|---------------------|  
|**进行动手实践：** 使用代码分析工具来指定自定义规则集以查找并修复简单的.NET Framework 应用程序中的问题。|-   [演练： 配置和使用自定义规则集](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)|  
|**配置项目的代码分析：** 选择现有规则集的项目、 Web 站点或解决方案。|-   [如何： 配置托管的代码项目的代码分析](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)<br />-   [使用规则集指定要运行的 c + + 规则](../code-quality/using-rule-sets-to-specify-the-cpp-rules-to-run.md)<br />-   [如何： 为 ASP.NET Web 应用程序配置代码分析](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)<br />-   [如何： 指定规则集的多个项目在解决方案中](../code-quality/how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution.md)|  
|**自定义规则集：** 指定规则适用于你的项目。|-   [创建自定义规则集](../code-quality/creating-custom-code-analysis-rule-sets.md)|  
|**了解内置规则集：** 查看构成了内置规则集的代码分析规则。|-   [代码分析规则集引用](../code-quality/code-analysis-rule-set-reference.md)|  
|**将代码分析与 Team Foundation Server 集成：** [!INCLUDE[esprtfs](../includes/esprtfs-md.md)]签入策略，以确保所有代码签入都符合一组常用的代码分析标准的开发团队。|-   [如何： 将代码项目规则集与团队项目签入策略同步](../code-quality/how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy.md)|



