---
title: 定义自定义 SharePoint 项目项类型 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint development in Visual Studio, defining new project item types
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d9b752aa8162f52746b4487b863557af6dd37fd9
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765575"
---
# <a name="define-custom-sharepoint-project-item-types"></a>定义自定义 SharePoint 项目项类型
  当你想要创建一种新的 SharePoint 项目项时，请定义一个新的 SharePoint 项目项类型。 例如，Visual Studio 不包括添加字段或自定义操作到 SharePoint 站点的 SharePoint 项目项。 你可以定义自己的用于创建字段、 自定义操作或其他类型的 SharePoint 组件的 SharePoint 项目项类型。  
  
## <a name="tasks-for-defining-sharepoint-project-item-types"></a>用于定义 SharePoint 项目项类型的任务
 若要定义的自定义项目项类型，生成的 Visual Studio 扩展程序集实现<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider>接口。 有关详细信息，请参阅[如何： 定义 SharePoint 项目项类型](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)。  
  
 当定义自定义项目项类型时，你还可以向项目项中添加以下功能：  
  
-   将快捷菜单项添加到项目项。 打开中的项目项的快捷菜单时显示的菜单项**解决方案资源管理器**通过右击项目项或通过选择它，然后选择**Shift** + **F10**密钥。 有关详细信息，请参阅[如何： 将快捷菜单项添加到自定义 SharePoint 项目项类型](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)。  
  
-   将自定义属性添加到项目项。 属性将显示在**属性**窗口时选择中的项目项**解决方案资源管理器**。 有关详细信息，请参阅[如何： 向自定义 SharePoint 项目项类型添加属性](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)。  
  
 若要启用其他开发人员可以使用 Visual Studio 中的项目项，创建一个.spdata 文件并创建项模板或与项目项关联的项目模板。 有关详细信息，请参阅[创建项模板和 SharePoint 项目项的项目模板](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)。  
  
## <a name="understand-the-relationship-between-project-item-types-and-project-item-instances"></a>了解项目项类型和项目项实例之间的关系
 在定义 SharePoint 项目项类型时，Visual Studio 将加载你的扩展关联的类型的项目项添加到 SharePoint 项目时。 例如，如果你定义了一个新**自定义操作**项目项类型，Visual Studio 加载你的扩展，当用户将添加**自定义操作**项目项的项目。 Visual Studio 将使用你的扩展的同一个实例关联的项目项类型的所有实例。 在上一示例中，如果用户将添加第二个**自定义操作**项项目到项目中，你的扩展的同一个实例用于自定义第二个项目项。  
  
 若要访问你的项目项类型的特定实例，处理之一<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents>的事件*projectItemTypeDefinition*的实现中的参数<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A>方法。 例如，若要确定你的自定义类型的项目项添加到项目时，处理<xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded>事件。 有关详细信息，请参阅[如何： 定义 SharePoint 项目项类型](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)。  
  
## <a name="see-also"></a>请参阅
 [如何： 定义 SharePoint 项目项类型](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [如何： 向自定义 SharePoint 项目项类型添加属性](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [如何： 将快捷菜单项添加到自定义 SharePoint 项目项类型](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)   
 [为 SharePoint 项目项创建项模板和项目模板](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [演练： 使用项模板创建的自定义操作项目项，第 1 部分](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [演练： 使用项目模板，第 1 部分中创建网站栏项目项](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [演练： 使用项模板创建的自定义操作项目项，第 2 部分](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)   
 [演练： 使用项目模板，第 2 部分中创建网站栏项目项](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)   
 [在 Visual Studio 中部署 SharePoint 工具扩展](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
