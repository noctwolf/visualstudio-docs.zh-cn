---
title: CA2227：集合属性应为只读
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
helpviewer_keywords:
- CA2227
- CollectionPropertiesShouldBeReadOnly
ms.assetid: 26967aaf-6fbe-438a-b4d3-ac579b5dc0f9
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: aa1d8644049f78eccfda7402360bdbc930b61601
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2018
---
# <a name="ca2227-collection-properties-should-be-read-only"></a>CA2227：集合属性应为只读

|||
|-|-|
|TypeName|CollectionPropertiesShouldBeReadOnly|
|CheckId|CA2227|
|类别|Microsoft.Usage|
|是否重大更改|重大|

## <a name="cause"></a>原因

外部可见，则可写属性属于类型实现<xref:System.Collections.ICollection?displayProperty=fullName>。 数组、 索引器 （与名为 Item 的属性） 和权限集，将忽略此规则。

## <a name="rule-description"></a>规则说明

使用可写的集合属性，用户可以将该集合替换为完全不同的集合。 只读属性禁止替换，该集合，但仍允许设置单个成员。 如果替换该集合是一个目标，首选的设计模式是包括的方法从集合中，删除所有元素和一个方法，以重新填充集合。 请参阅<xref:System.Collections.ArrayList.Clear%2A>和<xref:System.Collections.ArrayList.AddRange%2A>方法<xref:System.Collections.ArrayList?displayProperty=fullName>有关此模式的示例的类。

二进制和 XML 序列化支持是集合的只读属性。 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>类具有实现的类型的特定要求<xref:System.Collections.ICollection>和<xref:System.Collections.IEnumerable?displayProperty=fullName>才能可序列化。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复与此规则的冲突，请将该属性，只读的。 如果设计需要它，添加方法以清除并重新填充集合。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不要禁止显示此规则的警告。

## <a name="example"></a>示例

下面的示例显示的属性为可写的集合类型，并演示如何直接替换该集合。 此外，替换只读集合属性中使用的首选的方式`Clear`和`AddRange`显示方法。

[!code-csharp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CSharp/ca2227-collection-properties-should-be-read-only_1.cs)]
[!code-vb[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/VisualBasic/ca2227-collection-properties-should-be-read-only_1.vb)]
[!code-cpp[FxCop.Usage.PropertiesReturningCollections#1](../code-quality/codesnippet/CPP/ca2227-collection-properties-should-be-read-only_1.cpp)]

## <a name="related-rules"></a>相关的规则

[CA1819：属性不应返回数组](../code-quality/ca1819-properties-should-not-return-arrays.md)