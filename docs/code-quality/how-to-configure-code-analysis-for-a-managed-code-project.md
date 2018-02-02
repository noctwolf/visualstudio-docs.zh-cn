---
title: "如何： 配置托管的代码项目的代码分析 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codeanalysis.propertypages.csvb
helpviewer_keywords:
- code analysis, selecting rule sets
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 575b81e9c213e4025cd38921ad467869686d867c
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-configure-code-analysis-for-a-managed-code-project"></a>如何：配置托管代码项目的代码分析

在 Visual Studio 中，你可以从列表中选择的代码分析*规则集*要应用于托管的代码项目。 默认规则集是 Microsoft 最少量建议规则。 你可以应用另一个规则集对项目或解决方案中的所有项目。  
  
> [!NOTE]
> 有关如何配置 ASP.NET Web 应用程序设置的规则的信息，请参阅[如何： 为 ASP.NET Web 应用程序配置代码分析](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)。  
  
## <a name="to-configure-a-rule-set-for-a-net-framework-project"></a>若要配置的规则设置为.NET Framework 项目  
  
1.  在**解决方案资源管理器**，请单击该项目。  
  
2.  上**分析**菜单上，单击**的配置代码分析** *ProjectName*。  
  
3.  在**配置**和**平台**列表中，单击生成配置和目标平台。  
  
4.  若要运行代码分析，每次使用所选的配置生成项目时，选择**生成时启用代码分析**复选框。 你可以还手动运行代码分析通过打开**分析**菜单，选择 * * 对运行代码分析 * ProjectName * * *。  
  
5.  默认情况下，代码分析不报告由外部工具自动生成的代码所产生的警告。 若要查看生成的代码的警告，请清除**禁止显示生成代码产生的结果**复选框。  
  
    > [!NOTE]
    > 当生成的代码所产生的代码分析错误和警告出现在窗体和模板中时，此选项不会取消显示它们。 你可以查看和维护窗体或模板的源代码，而不会使覆盖。
  
6.  在**运行此规则集**列表中，执行下列操作之一：  
  
    -   单击你想要使用的规则集。  
  
    -   单击**\<浏览 … >**可以指定现有的自定义规则集不是在列表中。  
  
    -   定义自定义规则集。  
  
         有关详细信息，请参阅[创建自定义规则集](../code-quality/creating-custom-code-analysis-rule-sets.md)。  
  
## <a name="see-also"></a>请参阅

[演练：配置和使用自定义规则集](../code-quality/walkthrough-configuring-and-using-a-custom-rule-set.md)