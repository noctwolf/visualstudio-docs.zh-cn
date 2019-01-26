---
title: Outlook 解决方案
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], Outlook
- Office projects [Office development in Visual Studio], Outlook
- Office solutions [Office development in Visual Studio], Outlook
- templates [Office development in Visual Studio], Outlook
- projects [Office development in Visual Studio], Outlook
- Outlook [Office development in Visual Studio]
- e-mail [Office development in Visual Studio], Outlook solutions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 5537b07263cbdf48da9a0ce2e5705b8bd71941e9
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2019
ms.locfileid: "54870005"
---
# <a name="outlook-solutions"></a>Outlook 解决方案
  Visual Studio 提供可用于创建 Microsoft Office Outlook 的 VSTO 外接程序的项目模板。 VSTO 外接程序可用于自动执行 Outlook、扩展 Outlook 功能或自定义 Outlook 用户界面 (UI)。 有关 VSTO 外接程序的详细信息，请参阅 [Architecture of VSTO Add-ins](../vsto/architecture-of-vsto-add-ins.md)。  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
> [!NOTE]  
>  开发扩展的 Office 体验跨解决方案是否有兴趣[多个平台](https://dev.office.com/add-in-availability)？ 查看全新[Office 外接程序模型](https://dev.office.com/docs/add-ins/overview/office-add-ins)。 Office 外接程序具有较小的需求量与 VSTO 外接程序和解决方案，相比，您可以使用几乎任何 web 编程技术，HTML5、 JavaScript、 CSS3 和 XML 等来生成。  
  
## <a name="create-an-outlook-vsto-add-in-project"></a>创建一个 Outlook VSTO 外接程序项目  
 使用 **“新项目”** 对话框中的 **“Outlook 外接程序”** 项目模板，创建 Outlook 项目。 该模板包括所需的程序集引用和项目文件。  
  
 有关如何创建 VSTO 外接程序项目的详细信息，请参阅[如何：在 Visual Studio 中创建 Office 项目](../vsto/how-to-create-office-projects-in-visual-studio.md)。 有关项目模板的详细信息，请参阅[Office 项目模板概述](../vsto/office-project-templates-overview.md)。  
  
## <a name="outlook-vsto-add-in-programming-model"></a>Outlook VSTO 外接程序编程模型  
 在创建 Outlook VSTO 外接程序项目时，Visual Studio 将生成一个名为 `ThisAddIn`的类，这是你的解决方案的基础。 此类提供了写入代码的起点，并且还向 VSTO 外接程序公开 Outlook 的对象模型。  
  
 有关详细信息`ThisAddIn`类和其他功能，可在 VSTO 外接程序，请参阅[程序 VSTO 外接程序](../vsto/programming-vsto-add-ins.md)。  
  
## <a name="automate-outlook-by-using-the-outlook-object-model"></a>通过使用 Outlook 对象模型实现 Outlook 自动化  
 Outlook 对象模型公开了许多可用于实现 Outlook 自动化的模型。 这些类型使你能够编写代码来完成常规任务：  
  
- 以编程方式创建和发送电子邮件消息。  
  
- 发送新会议请求。  
  
- 搜索 Outlook 文件夹中的项。  
  
  有关详细信息，请参阅[Outlook 对象模型概述](../vsto/outlook-object-model-overview.md)。  
  
## <a name="customize-the-user-interface-of-an-outlook-application"></a>自定义 Outlook 应用程序的用户界面  
  
|任务|更多相关信息|  
|----------|--------------------------|  
|将自定义选项卡添加到 Outlook 检查器的功能区中。|[功能区概述](../vsto/ribbon-overview.md)|  
|将自定义组添加到 Outlook 检查器中的内置选项卡。|[如何：自定义内置选项卡](../vsto/how-to-customize-a-built-in-tab.md)|  
|添加一个在 Outlook 检查器中显示的自定义任务窗格|[自定义任务窗格](../vsto/custom-task-panes.md)。|  
|添加一个扩展或替换现有 Outlook 窗体的窗体区域。|[创建 Outlook 窗体区域](../vsto/creating-outlook-form-regions.md)|  
  
 有关自定义 Outlook 的 UI 和其他 Microsoft Office 应用程序的详细信息，请参阅[Office UI 自定义](../vsto/office-ui-customization.md)。  
  
## <a name="related-topics"></a>相关主题  
  
|标题|描述|  
|-----------|-----------------|  
|[Outlook 对象模型概述](../vsto/outlook-object-model-overview.md)|提供了由 Outlook 对象模型提供的对象概述。|  
|[创建 Outlook 窗体区域](../vsto/creating-outlook-form-regions.md)|介绍了 Visual Studio 提供的工具，可使你更轻松地设计、开发和调试窗体区域。|  
|[演练：在第一个 VSTO 外接程序为 Outlook 创建](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)|显示如何为 Microsoft Office Outlook 创建 VSTO 外接程序。|  
|[中的 Office 开发的 outlook 2010](http://go.microsoft.com/fwlink/?LinkId=199013)|MSDN Library 区域，可在其中找到有关开发 Outlook 解决方案的文章和参考文档（非特定于使用 Visual Studio 进行的 Office 开发）。|  
