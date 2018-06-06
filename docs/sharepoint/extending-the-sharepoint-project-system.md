---
title: 扩展 SharePoint 项目系统 |Microsoft 文档
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, extending projects
- SharePoint development in Visual Studio, extending project items
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: cabb70ba998594d99242696d0f87d60d5eb01226
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766083"
---
# <a name="extend-the-sharepoint-project-system"></a>扩展 SharePoint 项目系统
  你可以通过使用 Visual Studio 中的一组项目模板和项模板创建 SharePoint 解决方案。 这些模板满足许多的开发方案的要求，但您可能会发现某些情况下，它们不提供需要的功能。 在这些情况下，你可以扩展 SharePoint 项目系统。  
  
## <a name="overview-of-the-sharepoint-project-system"></a>SharePoint 项目系统的概述
 SharePoint 项目系统基于的基本组件*SharePoint 项目项*。 SharePoint 项目项表示的单个 SharePoint 自定义项，例如列表定义、 Web 部件或内容类型。  
  
 SharePoint 项目是一个包含一个或多个 SharePoint 项目项的 Visual Studio 项目。 SharePoint 项目还包含定义项目项功能和包部署到的分组方式的其他组件。  
  
 SharePoint 项目项和 SharePoint 项目的内容的详细信息，请参阅[创建项模板和 SharePoint 项目项的项目模板](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)。  
  
## <a name="how-to-extend-the-sharepoint-project-system"></a>如何扩展 SharePoint 项目系统
 你可以通过以下方式扩展 SharePoint 项目系统：  
  
-   定义你自己的 SharePoint 项目项类型，并将其与新项模板或 Visual Studio 中的项目模板关联。 例如，你可以创建自定义操作或字段定义 SharePoint 项目项类型。 有关详细信息，请参阅[定义自定义 SharePoint 项目项类型](../sharepoint/defining-custom-sharepoint-project-item-types.md)。  
  
-   扩展已安装在 Visual Studio 中的 SharePoint 项目项类型。 例如，你可以添加到中的项目项的快捷菜单项**解决方案资源管理器**和开发人员选择菜单项时自定义项目项。 有关详细信息，请参阅[扩展 SharePoint 项目项](../sharepoint/extending-sharepoint-project-items.md)。  
  
-   扩展 SharePoint 项目。 例如，你可以添加事件处理程序添加或移除 SharePoint 项目项时执行特定任务。 有关详细信息，请参阅[扩展 SharePoint 项目](../sharepoint/extending-sharepoint-projects.md)。  
  
-   扩展 SharePoint 项目项和 SharePoint 项目的打包和部署行为。 例如，你可以创建你自己的部署步骤来执行时或在部署或收回一个项目，Visual Studio 执行某些部署步骤时，你可以执行其他自定义任务。 有关详细信息，请参阅[扩展 SharePoint 打包和部署](../sharepoint/extending-sharepoint-packaging-and-deployment.md)。  
  
## <a name="common-development-tasks"></a>常见的开发任务
 扩展 SharePoint 项目系统中，可以执行以下常见任务：  
  
-   项目项与多种不同类型的项目文件中保存自定义字符串数据。 有关详细信息，请参阅[扩展 SharePoint 项目系统中保存数据](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)。  
  
-   将对象转换到 Visual Studio 自动化对象模型或集成对象模型中的相应对象的 SharePoint 项目系统中，反之亦然。 有关详细信息，请参阅[转换之间 SharePoint 项目系统类型和其他 Visual Studio 项目类型](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)。  
  
## <a name="see-also"></a>请参阅
 [定义自定义 SharePoint 项目项类型](../sharepoint/defining-custom-sharepoint-project-item-types.md)   
 [扩展 SharePoint 项目项](../sharepoint/extending-sharepoint-project-items.md)   
 [扩展 SharePoint 项目](../sharepoint/extending-sharepoint-projects.md)   
 [扩展 SharePoint 打包和部署](../sharepoint/extending-sharepoint-packaging-and-deployment.md)   
 [扩展 SharePoint 项目系统中保存数据](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md)   
 [SharePoint 项目系统类型和其他 Visual Studio 项目类型之间进行转换](../sharepoint/converting-between-sharepoint-project-system-types-and-other-visual-studio-project-types.md)   
 [扩展 Visual Studio 中的 SharePoint 工具](../sharepoint/extending-the-sharepoint-tools-in-visual-studio.md)   
 [SharePoint 工具扩展的编程概念和功能](../sharepoint/programming-concepts-and-features-for-sharepoint-tools-extensions.md)  
  
  
