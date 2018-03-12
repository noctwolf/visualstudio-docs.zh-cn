---
title: "ProjectItemFile 元素 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ProjectItemFile element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 7c222c25417f9a33f28871c94d8dd0d9353e1e76
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="projectitemfile-element"></a>ProjectItemFile 元素
  表示 SharePoint 文件，如功能元素文件中，要包括在项目项部署到 SharePoint 时。  
  
## <a name="syntax"></a>语法  
  
```  
<ProjectItemFile Source = "Name of the file"  
    Target = "Deployment path of the file"  
    Type = "Type of deployment for the file" />  
```  
  
## <a name="type"></a>类型  
 **ProjectItemFileType**  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|**源**|所需**xs: string**属性。<br /><br /> 要使用项目项部署的文件的名称。|  
|**Target**|可选**xs: string**属性。<br /><br /> 该文件将在其中部署 SharePoint, 部署根文件夹的相对路径。 部署根文件夹由指定的部署类型**类型**属性。 如果**目标**属性未指定，则文件将被部署到的文件夹中指定的名称与**源**属性。<br /><br /> 有关详细信息，请参阅说明**部署路径**和**部署根**属性的 SharePoint 项目中的项[开发 SharePoint 解决方案](../sharepoint/developing-sharepoint-solutions.md).|  
|**Type**|所需**xs: string**属性。<br /><br /> 部署的文件类型。 有关可能的值的详细信息，请参阅的描述**部署类型**属性中的 SharePoint 项目项[开发 SharePoint 解决方案](../sharepoint/developing-sharepoint-solutions.md)。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[文件](../sharepoint/files-element.md)|指定要包括在 SharePoint 项目项部署到 SharePoint 时的文件。|  
  
## <a name="remarks"></a>备注  
 通常在中引用的 SharePoint 文件**ProjectItemFile**元素包括功能元素文件 (Elements.xml)、 列表定义 (Schema.xml) 的架构文件和 Web 部件的 Web 部件 (.webpart) 的定义文件。  
  
## <a name="element-information"></a>元素信息  
  
|||  
|-|-|  
|**命名空间**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**架构名称**|SharePoint 项目项架构|  
|**验证文件**|ProjectItemModelSchema.xsd|  
|**可以为空**|否|  
  
## <a name="see-also"></a>请参阅  
 [SharePoint 项目项架构参考](../sharepoint/sharepoint-project-item-schema-reference.md)  
  
  