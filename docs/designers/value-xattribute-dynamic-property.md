---
title: 值（XAttribute 动态属性）
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: reference
apiname:
- XAttribute.Value
apitype: Assembly
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 473ff5b0124a050b60c9dc02929b2bad83f3661e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49842334"
---
# <a name="value-xattribute-dynamic-property"></a>值（XAttribute 动态属性）

获取或设置 XML 属性的值。

## <a name="syntax"></a>语法

```xaml
attrib.Value
```

## <a name="property-valuereturn-value"></a>属性值/返回值

包含此属性的值的 <xref:System.String>。

## <a name="exceptions"></a>异常

|异常类型|条件|
| - |---------------|
|<xref:System.ArgumentNullException>|设置时，`value` 为 `null`。|

## <a name="remarks"></a>备注

此属性等效于 <xref:System.Xml.Linq.XAttribute.Value%2A> 类的 <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> 属性，但此动态属性还支持更改通知。

## <a name="see-also"></a>请参阅

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [XAttribute 类动态属性](../designers/xattribute-class-dynamic-properties.md)
- [特性](../designers/attribute-xelement-dynamic-property.md)