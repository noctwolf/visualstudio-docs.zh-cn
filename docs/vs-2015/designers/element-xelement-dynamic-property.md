---
title: 元素（XElement 动态属性）| Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
api_name:
- XElement.Element
api_type:
- Assembly
ms.assetid: c6c25b8d-a1da-41ff-aeff-867ff1dcf749
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 879e5afb112df1f4c82cec150175b24456c1b0a4
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49256147"
---
# <a name="element-xelement-dynamic-property"></a>元素（XElement 动态属性）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

获取一个索引器，用于检索与指定扩展名对应的子元素实例。  
  
## <a name="syntax"></a>语法  
  
```  
elem.Element[{namespaceName}localName]  
```  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 一个类型为 `XElement Item(String expandedName)` 的索引器。 此索引器获取扩展名参数并返回相应的 <xref:System.Xml.Linq.XElement>，或者如果没有具有指定名称的元素，则返回 `null`。  
  
## <a name="remarks"></a>备注  
 此属性等效于 <xref:System.Xml.Linq.XContainer.Element%2A> 类的 <xref:System.Xml.Linq.XContainer?displayProperty=fullName> 方法。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>   
 [XElement 类动态属性](../designers/xelement-class-dynamic-properties.md)   
 [元素](../designers/elements-xelement-dynamic-property.md)



