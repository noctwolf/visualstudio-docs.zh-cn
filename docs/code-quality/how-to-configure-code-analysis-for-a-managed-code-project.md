---
title: 在 Visual Studio 中配置代码分析
ms.date: 04/04/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.csvb
- vs.codeanalysis.propertypages.solution
helpviewer_keywords:
- code analysis, selecting rule sets
- code analysis, rule sets
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: afa7a75ae083133f2cff1197b2aa111a1d7bf719
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-configure-code-analysis-for-a-managed-code-project"></a>如何：配置托管代码项目的代码分析

在 Visual Studio 中，你可以从列表中选择的代码分析*规则集*要应用于托管的代码项目。 默认规则集是*Microsoft 最少量建议规则*。 你可以应用另一个规则集对项目或解决方案中的所有项目。

> [!TIP]
> 有关如何配置 ASP.NET Web 应用程序设置的规则的信息，请参阅[如何： 为 ASP.NET Web 应用程序配置代码分析](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)。

## <a name="to-configure-a-rule-set-for-a-net-framework-project"></a>若要配置的规则设置为.NET Framework 项目

1. 打开**代码分析**项目的属性页上的选项卡。 可以通过以下方式之一来执行此操作：

   - 在**解决方案资源管理器**，选择项目。 在菜单栏上，选择**分析** > **配置代码分析** > **为\<projectname >**。

   - 右键单击中的项目**解决方案资源管理器**和选择**属性**，然后选择**代码分析**选项卡。

1. 在**配置**和**平台**列表中，选择生成配置和目标平台。

1. 若要运行代码分析，每次使用所选的配置生成项目时，选择**生成时启用代码分析**复选框。 你可以还手动运行代码分析通过选择**分析** > **运行代码分析** > **对运行代码分析\<projectname >**.

1. 默认情况下，代码分析不报告由外部工具自动生成的代码所产生的警告。 若要查看生成的代码的警告，请清除**禁止显示生成代码产生的结果**复选框。

    > [!NOTE]
    > 当生成的代码所产生的代码分析错误和警告出现在窗体和模板中时，此选项不会取消显示它们。 你可以查看和维护窗体或模板的源代码，而不会使覆盖。

1. 在**运行此规则集**列表中，执行下列操作之一：

    - 选择你想要使用的规则集。

    - 选择**\<浏览 … >** 查找现有的自定义规则集不在列表中。

    - 定义[自定义规则集](../code-quality/how-to-create-a-custom-rule-set.md)。

## <a name="specify-rule-sets-for-multiple-projects-in-a-solution"></a>在解决方案中指定多个项目规则的集

默认情况下，分配解决方案的所有托管的项目*Microsoft 最少量建议规则*代码分析规则集。 你可以更改分配给在解决方案中的项目的规则集**属性**解决方案的对话框。

1. 在 Visual Studio 中打开解决方案。

2. 上**分析**菜单上，选择**解决方案的配置代码分析**。

3. 如有必要，展开**通用属性**，然后选择**代码分析设置**。

4. 你可以指定一个或多个项目设置的规则：

    - 若要指定的规则集的单个项目，选择项目名称。

    - 若要指定设置为多个项目的规则，按住**Ctrl**并选择项目名称。

    - 若要在解决方案中指定的所有项目，请按住**Shift**并单击项目列表中。

5. 选择**规则集**规则的名称字段的一个项目，然后选择设置你想要应用。

## <a name="see-also"></a>请参阅

- [如何：为 ASP.NET Web 应用程序配置代码分析](../code-quality/how-to-configure-code-analysis-for-an-aspnet-web-application.md)