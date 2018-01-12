---
title: "如何： 创建 SharePoint Web 部件 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Web Parts [SharePoint development in Visual Studio], adding
- Web Parts [SharePoint development in Visual Studio], creating
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 27826859d2bac9b247132e7fcb2c3721b6d38092
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-create-a-sharepoint-web-part"></a>如何：创建 SharePoint Web 部件
  你可以创建和添加自定义 web 部件**Web 部件**到任何 SharePoint 项目项，然后编辑 web 部件或使用设计器的代码文件。 有关详细信息，请参阅[如何： 使用设计器创建 SharePoint Web 部件](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)。  
  
### <a name="to-create-a-sharepoint-web-part"></a>若要创建 SharePoint Web 部件  
  
1.  创建或打开一个 SharePoint 项目。  
  
     有关详细信息，请参阅[SharePoint 项目和项目项模板](../sharepoint/sharepoint-project-and-project-item-templates.md)。  
  
2.  选择中的 SharePoint 项目节点**解决方案资源管理器**，然后选择**项目**，**添加新项**。  
  
3.  在**添加新项**对话框框中，展开**SharePoint**节点，然后选择**2010年**节点。  
  
4.  在 SharePoint 模板列表中，选择**Web 部件**。  
  
5.  在**名称**框中，为 web 部件中，指定一个名称，然后选择**添加**按钮。  
  
     Web 部件显示在**解决方案资源管理器**。 有关 web 部件包括的文件的详细信息，请参阅[for SharePoint 创建 Web 部件](../sharepoint/creating-web-parts-for-sharepoint.md)。  
  
6.  在**解决方案资源管理器**，打开刚刚创建的 web 部件的代码文件。  
  
     例如，如果 Web 部件的名称为 WebPart1，请打开 WebPart1.vb（在 Visual Basic 中）或 WebPart1.cs（在 C# 中）。  
  
7.  在代码文件中，向 <xref:System.Web.UI.Control.CreateChildControls%2A> 方法添加控件。  
  
     有关示例，请参阅[演练： 为 SharePoint 创建 Web 部件](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)。  
  
## <a name="see-also"></a>请参阅  
 [为 SharePoint 创建 Web 部件](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [如何： 使用设计器创建 SharePoint Web 部件](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)   
 [演练： 为 SharePoint 创建 Web 部件](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)   
 [演练：使用设计器为 SharePoint 创建 Web 部件](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)  
  
  