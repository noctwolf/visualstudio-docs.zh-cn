---
title: 如何： 创建应用程序页 |Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- application pages [SharePoint development in Visual Studio], adding
- application pages [SharePoint development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9f390ddf14925b43f1aa1d9e79db05e2aa64f234
ms.sourcegitcommit: 0a8ac5f2a685270d9ca79bb39d26fd90099bfa29
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2018
ms.locfileid: "51296198"
---
# <a name="how-to-create-an-application-page"></a>如何： 创建应用程序页
  可以为一个或多个 SharePoint 网站创建 ASP.NET 网页。 在 SharePoint 中，这些页称为应用程序页。 与站点页上，不同的应用程序页包含页的后面运行的代码。 有关详细信息，请参阅[为 SharePoint 创建应用程序页](../sharepoint/creating-application-pages-for-sharepoint.md)。  
  
### <a name="to-create-an-application-page"></a>若要创建应用程序页  
  
1.  在 Visual Studio 中打开或创建一个 SharePoint 项目。  
  
     有关详细信息，请参阅[SharePoint 项目和项目项模板](../sharepoint/sharepoint-project-and-project-item-templates.md)。  
  
2.  在 **“解决方案资源管理器”** 中，选择项目节点。  
  
3.  在菜单栏上，依次选择“项目” > “添加新项”。  
  
4.  在中**添加新项**对话框框中，展开**SharePoint**节点，然后选择**2010年**项。  
  
5.  在 SharePoint 模板列表中，选择**应用程序页**。  
  
6.  在中**名称**框中，为应用程序页上，指定一个名称，然后选择**添加**按钮。  
  
     Visual Studio 将几个文件夹和文件添加到你的项目。 有关这些文件的详细信息，请参阅[为 SharePoint 创建应用程序页](../sharepoint/creating-application-pages-for-sharepoint.md)。  
  
     在中**源**Visual Web Developer 设计器中，ASP.NET 页文件的视图显示。 您可以通过将从控件添加设计页面**工具箱**并将其置于内容占位符上。 有关详细信息，请参阅[源视图、 网页设计器](/previous-versions/aspnet/ms178154\(v\=vs.100\))。  
  
7.  如果你要处理控件事件，请向应用程序页的代码文件添加代码。  
  
     代码文件显示如果展开 ASP.NET 页文件的节点，而且 *.cs*或 *.vb*扩展，具体取决于项目的语言。 有关如何创建应用程序页的端到端示例，请参阅[演练： 创建 SharePoint 应用程序页](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)。  
  
## <a name="see-also"></a>请参阅
 [为 SharePoint 创建应用程序页](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [演练： 创建 SharePoint 应用程序页](../sharepoint/walkthrough-creating-a-sharepoint-application-page.md)  
  
