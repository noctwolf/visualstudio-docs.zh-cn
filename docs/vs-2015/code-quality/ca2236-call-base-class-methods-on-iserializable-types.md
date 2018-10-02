---
title: CA2236： 对 ISerializable 类型调用基类方法 |Microsoft Docs
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
- CA2236
- CallBaseClassMethodsOnISerializableTypes
helpviewer_keywords:
- CA2236
- CallBaseClassMethodsOnISerializableTypes
ms.assetid: 5a15b20d-769c-4640-b31a-36e07077daae
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 1219e1c2252565e671d73924f5ac96ba00ecef18
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "47587763"
---
# <a name="ca2236-call-base-class-methods-on-iserializable-types"></a>CA2236：对 ISerializable 类型调用基类方法
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA2236： 对 ISerializable 类型调用基类方法](https://docs.microsoft.com/visualstudio/code-quality/ca2236-call-base-class-methods-on-iserializable-types)。

|||
|-|-|
|TypeName|CallBaseClassMethodsOnISerializableTypes|
|CheckId|CA2236|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 一个类型派生的类型实现<xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>接口，并且以下条件之一为 true:

-   该类型实现序列化构造函数中，即，构造函数与<xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>，<xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>参数签名，但不会调用基类型的序列化构造函数。

-   该类型实现<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName>方法，但不会调用<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>基类型的方法。

## <a name="rule-description"></a>规则说明
 在自定义序列化过程中，某个类型实现<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>方法以序列化其字段和序列化构造函数进行反序列化字段。 如果该类型派生自实现的类型<xref:System.Runtime.Serialization.ISerializable>接口的基类型<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>方法和序列化构造函数都应调用到序列化/反序列化基类型的字段。 否则为该类型将不序列化，正确地反序列化。 请注意，是否派生的类型不添加任何新的字段，该类型不需要实现<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>方法，也不序列化构造函数或调用基类型等效项。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请调用基类型<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>方法或序列化构造函数从对应派生类型方法或构造函数。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例所示通过调用序列化构造函数来满足该规则的派生的类型和<xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>基类的方法。

 [!code-csharp[FxCop.Usage.CallBaseISerializable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.CallBaseISerializable/cs/FxCop.Usage.CallBaseISerializable.cs#1)]
 [!code-vb[FxCop.Usage.CallBaseISerializable#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.CallBaseISerializable/vb/FxCop.Usage.CallBaseISerializable.vb#1)]

## <a name="related-rules"></a>相关的规则
 [CA2240：正确实现 ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229：实现序列化构造函数](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238：正确实现序列化方法](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235：标记所有不可序列化的字段](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237：以 SerializableAttribute 标记 ISerializable 类型](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2239：为可选字段提供反序列化方法](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)

 [CA2120：保护序列化构造函数](../code-quality/ca2120-secure-serialization-constructors.md)



