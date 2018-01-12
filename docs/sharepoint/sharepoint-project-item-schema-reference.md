---
title: "SharePoint 项目项架构参考 |Microsoft 文档"
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
helpviewer_keywords:
- FeatureProperty element
- SafeControls element
- SafeControl element
- .spdata files
- ExtensionData element
- FeatureProperties element
- ProjectOutputFile element
- Files element
- ProjectItemFolder element
- ProjectItemFile element
- ExtensionDataItem element
- ProjectItem element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 99a2471919483f02a9f58a35ad164527a12a39c5
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="sharepoint-project-item-schema-reference"></a>SharePoint 项目项架构参考
  Visual Studio 使用 SharePoint 项目项架构来验证.spdata 文件的内容。 .Spdata 文件指定的内容和行为的 SharePoint 项目项。 SharePoint 项目项的内容的详细信息，请参阅[创建项模板和 SharePoint 项目项的项目模板](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)。  
  
 SharePoint 项目项架构名为 ProjectItemModelSchema.xsd 且已安装在 %Program Files (x86)%\Microsoft Visual Studio 11.0\Xml\Schemas 默认情况下。  
  
 根元素是[ProjectItem](../sharepoint/projectitem-element.md)元素。 下表介绍的所有元素的架构定义。  
  
|元素|描述|  
|-------------|-----------------|  
|[ExtensionData](../sharepoint/extensiondata-element.md)|表示自定义数据与 SharePoint 项目项关联的项的集合。|  
|[ExtensionDataItem](../sharepoint/extensiondataitem-element.md)|表示键/值格式中的 SharePoint 项目项与相关联的自定义数据项。 键和值必须为字符串。|  
|[FeatureProperties](../sharepoint/featureproperties-element.md)|表示部署到 SharePoint 时所包含的一项功能的属性值的集合。 将功能部署后，你可以在代码中访问属性值。|  
|[FeatureProperty](../sharepoint/featureproperty-element.md)|表示将其部署到 SharePoint 时所随附一项功能的自定义属性。 将功能部署后，你可以在代码中访问属性。|  
|[文件](../sharepoint/files-element.md)|指定要部署使用 SharePoint 项目项，如功能元素文件或项目的输出的文件。|  
|[项目项](../sharepoint/projectitem-element.md)|表示一个 SharePoint 项目项。|  
|[ProjectItemFile](../sharepoint/projectitemfile-element.md)|表示 SharePoint 文件，如功能元素文件中，要包括在项目项部署到 SharePoint 时。|  
|[ProjectItemFolder](../sharepoint/projectitemfolder-element.md)|表示映射的文件夹。|  
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|表示要部署到 SharePoint 项目项包含项目的输出。|  
|[SafeControl](../sharepoint/safecontrol-element.md)|表示一个 ASPX 控件或指定为安全的任何用户访问 SharePoint 站点上的任意 ASPX 页上的 Web 部件。|  
|[SafeControls](../sharepoint/safecontrols-element.md)|表示 ASPX 控件和指定为安全的任何用户访问 SharePoint 站点上的任意 ASPX 页上的 Web 部件的集合。|  
  
## <a name="see-also"></a>请参阅  
 [为 SharePoint 项目项创建项模板和项目模板](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)  
  
  