---
title: Xml（XElement 动态属性）
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: reference
apiname:
- XElement.Xml
ms.assetid: 69ab2a33-4fe7-4cfa-97f8-eaf063decb18
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 36b2100218267587e2ea5d38ad62f7ed28dbc102
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="xml-xelement-dynamic-property"></a>Xml（XElement 动态属性）

获取元素的非格式化 XML 内容。

## <a name="syntax"></a>语法

```
elem.Xml
```

## <a name="property-valuereturn-value"></a>属性值/返回值

表示元素的非格式化 XML 内容的 <xref:System.String>。

## <a name="remarks"></a>备注

此属性等效于 <xref:System.Xml.Linq.XNode.ToString(System.Xml.Linq.SaveOptions)> 类的 <xref:System.Xml.Linq.XNode?displayProperty=fullName> 方法，其 `SaveOptions` 参数设置为 <xref:System.Xml.Linq.SaveOptions>。

## <a name="see-also"></a>请参阅

- [XElement 类动态属性](../designers/xelement-class-dynamic-properties.md)
- [值](../designers/value-xelement-dynamic-property.md)