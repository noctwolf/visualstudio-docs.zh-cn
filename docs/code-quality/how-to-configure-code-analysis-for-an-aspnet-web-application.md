---
title: 如何： 在 Visual Studio 中为 ASP.NET Web 应用程序配置代码分析
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.asp
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 4d950846811cf1792bf2ee302d37ebd686107fe6
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-configure-code-analysis-for-an-aspnet-web-application"></a>如何：为 ASP.NET Web 应用程序配置代码分析

在 Visual Studio 中，可以从列表中选择的代码分析*规则集*要应用于[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]Web 应用程序。 默认规则集是 Microsoft 最少量建议规则。 你可以选择另一个规则集以将应用于 Web 站点。

1. 选择中的 Web 站点**解决方案资源管理器**。

2. 上**分析**菜单上，单击**为网站配置代码分析**。

3. 如果你选择解决方案，并且该解决方案包含多个项目，选择生成配置和目标操作系统从**配置**和**平台**列出。

4. 对于每个项目解决方案中，单击**规则集**列，，然后单击该规则的名称设置为运行。

5. 默认情况下，在解决方案中的所有项目运行代码分析。 若要禁用或启用特定项目的代码分析，请按照下列步骤：

    1. 右键单击项目名称，然后单击属性。

    2. 选中或清除**时启用代码分析**复选框。 你可以还手动运行代码分析通过选择**Web 站点上运行代码分析**从**分析**菜单。

6. 在**运行此规则集**下拉列表中，请按照下列步骤：

    - 选择你想要使用的规则集。

    - 选择**\<浏览 >** 可以指定现有的自定义规则集不是在列表中。

    - 定义[自定义规则集](../code-quality/how-to-create-a-custom-rule-set.md)。