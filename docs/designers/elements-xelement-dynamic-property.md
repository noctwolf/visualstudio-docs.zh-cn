---
title: "元素（XElement 动态属性）| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
apiname: XElement.Elements
apitype: Assembly
ms.assetid: 3d5737f2-d2ed-410a-821c-349dbb2b574f
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8c8bca4053da38738068c14fc20b43acc6c775ac
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="elements-xelement-dynamic-property"></a>元素（XElement 动态属性）
获取一个索引器，用于检索与指定扩展名匹配的当前元素的子元素。  
  
## <a name="syntax"></a>语法  
  
```  
elem.Elements[{namespaceName}localName]   
```  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 一个类型为 `IEnumerable<XElement> Item(String expandedName)` 的索引器。 此索引器获取所需子元素的扩展名，并返回 <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` 集合中的匹配子元素。  
  
## <a name="remarks"></a>备注  
 此属性等效于 <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> 类的 <xref:System.Xml.Linq.XContainer> 方法。  
  
 返回集合中的元素按 XML 源文档顺序排列。  
  
 此属性使用延迟执行。  
  
## <a name="see-also"></a>请参阅  
 [XElement 类动态属性](../designers/xelement-class-dynamic-properties.md)   
 [元素](../designers/element-xelement-dynamic-property.md)   
 [子代](../designers/descendants-xelement-dynamic-property.md)