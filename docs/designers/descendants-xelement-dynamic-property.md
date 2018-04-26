---
title: 子代（XElement 动态属性）
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: reference
ms.assetid: 9611d00f-23bf-444b-ab0c-f30701bfc13d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7c1b0aa0c55c0da2a6f9af58f5d54ff607a409ce
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="descendants-xelement-dynamic-property"></a>子代（XElement 动态属性）

获取一个索引器，用于检索与指定扩展名匹配的当前元素的所有子代元素。

## <a name="syntax"></a>语法

```
elem.Descendants[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>属性值/返回值

一个类型为 `IEnumerable<XElement> Item(String expandedName)` 的索引器。 此索引器获取指定子代元素的扩展名，并返回 <xref:System.Collections.IEnumerable>`<`<xref:System.Xml.Linq.XElement>`>` 集合中的匹配子元素。

## <a name="remarks"></a>备注

此属性等效于 <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> 类的 <xref:System.Xml.Linq.XContainer> 方法。

返回集合中的元素按 XML 源文档顺序排列。

此属性使用延迟执行。

## <a name="see-also"></a>请参阅

- [XElement 类动态属性](../designers/xelement-class-dynamic-properties.md)
- [元素](../designers/elements-xelement-dynamic-property.md)