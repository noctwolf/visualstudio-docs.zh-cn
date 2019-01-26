---
title: FeatureProperties 元素 |Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- FeatureProperties element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: fb345e66a53f9816281df6e948a8961252c0fcea
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2019
ms.locfileid: "54862584"
---
# <a name="featureproperties-element"></a>FeatureProperties 元素
  部署到 SharePoint 时，包含与某个功能的属性值的集合。 将功能部署后，你可以在代码中访问的属性值。  
  
## <a name="syntax"></a>语法  
  
```xml  
<FeatureProperties>  
  <FeatureProperty.../>  
</FeatureProperties>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素
  
|元素|描述|  
|-------------|-----------------|  
|[FeatureProperty](../sharepoint/featureproperty-element.md)|可选元素。<br /><br /> 表示键/值格式中的自定义属性。|  
  
### <a name="parent-elements"></a>父元素
  
|元素|描述|  
|-------------|-----------------|  
|[ProjectItem](../sharepoint/projectitem-element.md)|表示 SharePoint 项目项。 此元素的必需的根元素的`.spdata`文件。|  
  
## <a name="remarks"></a>备注  
 功能属性的详细信息，请参阅[提供在项目项中的打包和部署信息](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)。  
  
## <a name="element-information"></a>元素信息
  
|元素|描述|  
|-------------|-----------------|  
|**命名空间**|http<nolink>://schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|  
|**架构名称**|SharePoint 项目项架构|  
|**验证文件**|ProjectItemModelSchema.xsd|  
|**可以为空**|否|  
  
## <a name="see-also"></a>请参阅
 [SharePoint 项目项架构参考](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [提供在项目项中的打包和部署信息](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)  
