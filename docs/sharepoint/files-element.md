---
title: 文件元素 |Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Files element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b25bb220d3c22af280a486de115193af38c85dbe
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2019
ms.locfileid: "54864522"
---
# <a name="files-element"></a>Files 元素
  指定要部署使用 SharePoint 项目项，如功能元素文件和依赖的非 SharePoint 项目的输出的文件。  
  
## <a name="syntax"></a>语法  
  
```xml  
<Files>  
  <ProjectItemFile.../>  
  <ProjectOutputFile.../>  
</Files>  
```  
  
## <a name="type"></a>类型  
 **FileCollectionType**  
  
## <a name="attributes-and-elements"></a>特性和元素
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素
  
|元素|描述|  
|-------------|-----------------|  
|[ProjectItemFile](../sharepoint/projectitemfile-element.md)|可选**ProjectItemFileType**元素。<br /><br /> 表示 SharePoint 文件，如功能元素文件部署到 SharePoint 时，包含与项目项。|  
|[ProjectOutputFile](../sharepoint/projectoutputfile-element.md)|可选**ProjectOutputFileType**元素。<br /><br /> 表示要部署到 SharePoint 时，包含与项目项的项目的输出。|  
  
### <a name="parent-elements"></a>父元素
  
|元素|描述|  
|-------------|-----------------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|表示 SharePoint 项目项。 此元素的必需的根元素的`.spdata`文件。|  
  
## <a name="element-information"></a>元素信息
  
|||  
|-|-|  
|**命名空间**|http<nolink>://schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|  
|**架构名称**|SharePoint 项目项架构|  
|**验证文件**|ProjectItemModelSchema.xsd|  
|**可以为空**|否|  
  
## <a name="see-also"></a>请参阅
 [SharePoint 项目项架构参考](../sharepoint/sharepoint-project-item-schema-reference.md)  
