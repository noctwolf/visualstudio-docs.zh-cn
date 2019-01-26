---
title: SharePoint 项目项架构参考 |Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
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
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: c261115b21d1067b7494d09ad8031b3f4dc5a8c5
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2019
ms.locfileid: "54864912"
---
# <a name="sharepoint-project-item-schema-reference"></a>SharePoint 项目项架构参考
  Visual Studio 将使用 SharePoint 项目项架构验证的内容 *.spdata*文件。 *.Spdata*文件指定的内容和 SharePoint 项目项的行为。 SharePoint 项目项的内容的详细信息，请参阅[创建项模板和项目模板的 SharePoint 项目项](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)。  
  
 SharePoint 项目项架构名为 ProjectItemModelSchema.xsd 和在 %Program Files (x86)%\Microsoft Visual Studio 11.0\Xml\Schemas 默认情况下安装。  
  
 根元素是[ProjectItem](../sharepoint/projectitem-element.md)元素。 下表介绍的所有元素架构定义。  
  
|元素|描述|  
|-------------|-----------------|  
|[ExtensionData](../sharepoint/extensiondata-element.md)|表示 SharePoint 项目项与相关联的自定义数据项的集合。|  
|[ExtensionDataItem](../sharepoint/extensiondataitem-element.md)|表示键/值格式中的 SharePoint 项目项与相关联的自定义数据项。 键和值必须为字符串。|  
|[FeatureProperties](../sharepoint/featureproperties-element.md)|表示部署到 SharePoint 时，包含与某个功能的属性值的集合。 将功能部署后，你可以在代码中访问的属性值。|  
|[FeatureProperty](../sharepoint/featureproperty-element.md)|表示部署到 SharePoint 时，将包括与某个功能的自定义属性。 将功能部署后，您可以在代码中访问属性。|  
|[文件](../sharepoint/files-element.md)|指定要使用的 SharePoint 项目项，如功能元素文件或项目的输出进行部署的文件。|  
|[ProjectItem](../sharepoint/projectitem-element.md)|表示 SharePoint 项目项。|  
|[ProjectItemFile](../sharepoint/projectitemfile-element.md)|表示 SharePoint 文件，如功能元素文件部署到 SharePoint 时，包含与项目项。|  
|[ProjectItemFolder](../sharepoint/projectitemfolder-element.md)|表示映射的文件夹。|  
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|表示要部署到 SharePoint 时，包含与项目项的项目的输出。|  
|[SafeControl](../sharepoint/safecontrol-element.md)|表示一个 ASPX 控件或指定为安全的任何用户访问 SharePoint 站点上任何 ASPX 页上的 Web 部件。|  
|[SafeControls](../sharepoint/safecontrols-element.md)|表示的 ASPX 控件和指定为安全的任何用户访问 SharePoint 站点上任何 ASPX 页上的 Web 部件的集合。|  
  
## <a name="see-also"></a>请参阅
 [创建项模板和用于 SharePoint 项目项的项目模板](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)  
