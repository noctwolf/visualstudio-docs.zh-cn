---
title: CA2236:对 ISerializable 类型调用基类方法
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
helpviewer_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
ms.assetid: 5a15b20d-769c-4640-b31a-36e07077daae
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2ed7249925f066cdbba7616b368e80e7b8126bca
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54935992"
---
# <a name="ca2236-call-base-class-methods-on-iserializable-types"></a>CA2236:对 ISerializable 类型调用基类方法

|||
|-|-|
|TypeName|CallBaseClassMethodsOnISerializableTypes|
|CheckId|CA2236|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 一个类型派生的类型实现<xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>接口，并且以下条件之一为 true:

- 该类型实现序列化构造函数中，即，构造函数与<xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>，<xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>参数签名，但不会调用基类型的序列化构造函数。

- 该类型实现<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName>方法，但不会调用<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>基类型的方法。

## <a name="rule-description"></a>规则说明
 在自定义序列化过程中，某个类型实现<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>方法以序列化其字段和序列化构造函数进行反序列化字段。 如果该类型派生自实现的类型<xref:System.Runtime.Serialization.ISerializable>接口的基类型<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>方法和序列化构造函数都应调用到序列化/反序列化基类型的字段。 否则为该类型将不序列化，正确地反序列化。 请注意，是否派生的类型不添加任何新的字段，该类型不需要实现<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>方法，也不序列化构造函数或调用基类型等效项。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请调用基类型<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>方法或序列化构造函数从对应派生类型方法或构造函数。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例所示通过调用序列化构造函数来满足该规则的派生的类型和<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>基类的方法。

 [!code-vb[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/VisualBasic/ca2236-call-base-class-methods-on-iserializable-types_1.vb)]
 [!code-csharp[FxCop.Usage.CallBaseISerializable#1](../code-quality/codesnippet/CSharp/ca2236-call-base-class-methods-on-iserializable-types_1.cs)]

## <a name="related-rules"></a>相关的规则
 [CA2240:正确实现 ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229：实现序列化构造函数](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238:正确实现序列化方法](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235:标记所有不可序列化的字段](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237:用 SerializableAttribute 标记 ISerializable 类型](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2239:提供反序列化方法为可选字段](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120:安全的序列化构造函数](../code-quality/ca2120-secure-serialization-constructors.md)