---
title: 值（XAttribute 动态属性）|Microsoft Docs
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
- XAttribute.Value
api_type:
- Assembly
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bd9ea1fa163980a39bcd9981b9e1d757d72fcb6a
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49229146"
---
# <a name="value-xattribute-dynamic-property"></a>值（XAttribute 动态属性）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

获取或设置 XML 属性的值。  
  
## <a name="syntax"></a>语法  
  
```  
attrib.Value   
```  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 包含此属性的值的 <xref:System.String>。  
  
## <a name="exceptions"></a>异常  
  
|异常类型|条件|  
|--------------------|---------------|  
|<xref:System.ArgumentNullException>|设置时，`value` 为 `null`。|  
  
## <a name="remarks"></a>备注  
 此属性等效于 <xref:System.Xml.Linq.XAttribute.Value%2A> 类的 <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> 属性，但此动态属性还支持更改通知。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>   
 [XAttribute 类动态属性](../designers/xattribute-class-dynamic-properties.md)   
 [特性](../designers/attribute-xelement-dynamic-property.md)



