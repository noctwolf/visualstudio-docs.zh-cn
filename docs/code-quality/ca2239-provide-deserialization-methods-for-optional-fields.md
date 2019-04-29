---
title: CA2239:为可选字段提供反序列化方法
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2239
- ProvideDeserializationMethodsForOptionalFields
helpviewer_keywords:
- ProvideDeserializationMethodsForOptionalFields
- CA2239
ms.assetid: 6480ff5e-0caa-4707-814e-2f927cdafef5
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 5599f111d6580f654436fdd2ff85f69f1329920d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541631"
---
# <a name="ca2239-provide-deserialization-methods-for-optional-fields"></a>CA2239:为可选字段提供反序列化方法

|||
|-|-|
|TypeName|ProvideDeserializationMethodsForOptionalFields|
|CheckId|CA2239|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 类型具有字段标有<xref:System.Runtime.Serialization.OptionalFieldAttribute?displayProperty=fullName>属性和类型不提供反序列化事件处理方法。

## <a name="rule-description"></a>规则说明
 <xref:System.Runtime.Serialization.OptionalFieldAttribute>属性在序列化没有影响; 用特性标记的字段进行序列化。 但是，该字段上反序列化，将忽略，并且会保留其类型与关联的默认值。 反序列化事件处理程序应声明为要在反序列化过程中设置的字段。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请添加反序列化事件处理方法的类型。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它可以安全地禁止显示此规则的警告，如果应在反序列化过程中忽略该字段。

## <a name="example"></a>示例
 下面的示例演示具有可选字段和反序列化事件的类型处理方法。

 [!code-csharp[FxCop.Usage.OptionalFields#1](../code-quality/codesnippet/CSharp/ca2239-provide-deserialization-methods-for-optional-fields_1.cs)]
 [!code-vb[FxCop.Usage.OptionalFields#1](../code-quality/codesnippet/VisualBasic/ca2239-provide-deserialization-methods-for-optional-fields_1.vb)]

## <a name="related-rules"></a>相关的规则
 [CA2236:对 ISerializable 类型调用基类方法](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240:正确实现 ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229：实现序列化构造函数](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238:正确实现序列化方法](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235：标记所有不可序列化的字段](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237：用 SerializableAttribute 标记 ISerializable 类型](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2120:安全的序列化构造函数](../code-quality/ca2120-secure-serialization-constructors.md)