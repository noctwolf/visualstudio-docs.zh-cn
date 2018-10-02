---
title: CA2235： 标记所有不可序列化字段 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2235
- MarkAllNonSerializableFields
helpviewer_keywords:
- CA2235
- MarkAllNonSerializableFields
ms.assetid: 599ad877-3a15-426c-bf17-5de15427365f
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 025ee336052bdad010b55e1ba804b2bd37c7e0d7
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "47587688"
---
# <a name="ca2235-mark-all-non-serializable-fields"></a>CA2235：标记所有不可序列化的字段
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA2235： 标记所有不可序列化字段](https://docs.microsoft.com/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields)。

|||
|-|-|
|TypeName|MarkAllNonSerializableFields|
|CheckId|CA2235|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 在可以序列化的类型中声明了类型不可序列化的实例字段。

## <a name="rule-description"></a>规则说明
 可序列化类型是指将标有<xref:System.SerializableAttribute?displayProperty=fullName>属性。 当序列化类型时，<xref:System.Runtime.Serialization.SerializationException?displayProperty=fullName>类型包含不可序列化的类型的实例字段而引发异常。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请应用<xref:System.NonSerializedAttribute?displayProperty=fullName>属性不是可序列化的字段。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果仅禁止显示此规则的警告<xref:System.Runtime.Serialization.ISerializationSurrogate?displayProperty=fullName>类型被声明为允许要进行序列化和反序列化的字段的实例。

## <a name="example"></a>示例
 下面的示例演示了违反规则的类型，并满足该规则的类型。

 [!code-csharp[FxCop.Usage.MarkNonSerializable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkNonSerializable/cs/FxCop.Usage.MarkNonSerializable.cs#1)]
 [!code-vb[FxCop.Usage.MarkNonSerializable#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkNonSerializable/vb/FxCop.Usage.MarkNonSerializable.vb#1)]

## <a name="related-rules"></a>相关的规则
 [CA2236：对 ISerializable 类型调用基类方法](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240：正确实现 ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229：实现序列化构造函数](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238：正确实现序列化方法](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2237：以 SerializableAttribute 标记 ISerializable 类型](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2239：为可选字段提供反序列化方法](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120：保护序列化构造函数](../code-quality/ca2120-secure-serialization-constructors.md)



