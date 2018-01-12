---
title: "ProjectItemFolder 元素 |Microsoft 文档"
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
helpviewer_keywords: ProjectItemFolder element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: df3c5b91e5f95d6ec794bff08c2251c5bf5e5307
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="projectitemfolder-element"></a>ProjectItemFolder 元素
  表示映射的文件夹。  
  
## <a name="syntax"></a>语法  
  
```  
<ProjectItemFolder Target = "Path of SharePoint folder the mapped folder corresponds to"  
    Type = "Type of deployment for the mapped folder" />  
```  
  
## <a name="type"></a>类型  
 **ProjectItemFolderType**  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|**Target**|所需**xs: string**属性。<br /><br /> 在 SharePoint 安装的映射的文件夹对应，相对于部署根文件夹中文件夹的路径。 部署根文件夹由指定的部署类型**类型**属性。<br /><br /> 有关详细信息，请参阅说明**部署路径**和**部署根**属性的 SharePoint 项目中的项[开发 SharePoint 解决方案](../sharepoint/developing-sharepoint-solutions.md).|  
|**Type**|所需**xs: string**属性。<br /><br /> 映射的文件夹的部署类型。 有关可能的值的详细信息，请参阅的描述**部署类型**属性中的 SharePoint 项目项[开发 SharePoint 解决方案](../sharepoint/developing-sharepoint-solutions.md)。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[项目项](../sharepoint/projectitem-element.md)|表示一个 SharePoint 项目项。 这是.spdata 文件的所需的根元素。|  
  
## <a name="remarks"></a>备注  
 有关映射的文件夹的详细信息，请参阅[如何： 添加和移除映射文件夹](../sharepoint/how-to-add-and-remove-mapped-folders.md)。  
  
## <a name="element-information"></a>元素信息  
  
|||  
|-|-|  
|**命名空间**|http://schemas.microsoft.com/VisualStudio/2010/SharePointTools/SharePointProjectItemModel|  
|**架构名称**|SharePoint 项目项架构|  
|**验证文件**|ProjectItemModelSchema.xsd|  
|**可以为空**|否|  
  
## <a name="see-also"></a>请参阅  
 [SharePoint 项目项架构参考](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [如何：添加和删除映射文件夹](../sharepoint/how-to-add-and-remove-mapped-folders.md)  
  
  