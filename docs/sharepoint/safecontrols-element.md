---
title: SafeControls 元素 |Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SafeControls element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: fe8b3c026b7386d89ef04d0a966eccad425f1629
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37118780"
---
# <a name="safecontrols-element"></a>SafeControls 元素
  ASPX 控件和指定的任何用户访问 SharePoint 站点上任何 ASPX 页上的安全的 Web 部件的集合。  
  
## <a name="syntax"></a>语法  
  
```xml  
<SafeControls>  
  <SafeControl.../>  
</SafeControls>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素
  
|元素|描述|  
|-------------|-----------------|  
|[SafeControl](../sharepoint/safecontrol-element.md)|可选元素。<br /><br /> 表示一个 ASPX 控件或指定为安全的任何用户访问 SharePoint 站点上任何 ASPX 页上的 Web 部件。|  
  
### <a name="parent-elements"></a>父元素
  
|元素|描述|  
|-------------|-----------------|  
|[项目项](../sharepoint/projectitem-element.md)|表示 SharePoint 项目项。 此元素的必需的根元素的 *.spdata*文件。|  
  
## <a name="remarks"></a>备注  
 有关安全控件的详细信息，请参阅[提供在项目项中的打包和部署信息](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)。  
  
## <a name="element-information"></a>元素信息
  
|||  
|-|-|  
|**命名空间**|http<nolink>: //schemas.microsoft.com/VisualStudio/<br>2010/SharePointTools/SharePointProjectItemModel|  
|**架构名称**|SharePoint 项目项架构|  
|**验证文件**|ProjectItemModelSchema.xsd|  
|**可以为空**|否|  
  
## <a name="see-also"></a>请参阅
 [SharePoint 项目项架构参考](../sharepoint/sharepoint-project-item-schema-reference.md)   
 [提供在项目项中的打包和部署信息](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)  
  
