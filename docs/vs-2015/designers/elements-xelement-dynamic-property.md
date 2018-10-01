---
title: 元素（XElement 动态属性）| Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
api_name:
- XElement.Elements
api_type:
- Assembly
ms.assetid: 3d5737f2-d2ed-410a-821c-349dbb2b574f
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 75cb7f8f6a5259151679ecee84bbeb5db336782f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471355"
---
# <a name="elements-xelement-dynamic-property"></a>元素（XElement 动态属性）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[元素 （XElement 动态属性）](https://docs.microsoft.com/visualstudio/designers/elements-xelement-dynamic-property)。  
  
获取一个索引器，用于检索与指定扩展名匹配的当前元素的子元素。  
  
## <a name="syntax"></a>语法  
  
```  
elem.Elements[{namespaceName}localName]   
```  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 一个类型为 `IEnumerable<XElement> Item(String expandedName)` 的索引器。 此索引器获取所需子元素的扩展名，并返回 <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` 集合中的匹配子元素。  
  
## <a name="remarks"></a>备注  
 此属性等效于 <xref:System.Xml.Linq.XContainer.Elements%28System.Xml.Linq.XName%29?displayProperty=fullName> 类的 <xref:System.Xml.Linq.XContainer> 方法。  
  
 返回集合中的元素按 XML 源文档顺序排列。  
  
 此属性使用延迟执行。  
  
## <a name="see-also"></a>请参阅  
 [XElement 类动态属性](../designers/xelement-class-dynamic-properties.md)   
 [元素](../designers/element-xelement-dynamic-property.md)   
 [子代](../designers/descendants-xelement-dynamic-property.md)



