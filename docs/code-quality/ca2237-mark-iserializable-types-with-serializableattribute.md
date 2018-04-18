---
title: CA2237： 以 SerializableAttribute 标记 ISerializable 类型 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2237
- MarkISerializableTypesWithSerializable
helpviewer_keywords:
- MarkISerializableTypesWithSerializable
- CA2237
ms.assetid: 9bd6bb24-a527-43dd-9952-043c0c694f46
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b9b4c0d05e972b4cf9a84677ccbc7d15d117c3f0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ca2237-mark-iserializable-types-with-serializableattribute"></a>CA2237：以 SerializableAttribute 标记 ISerializable 类型
|||  
|-|-|  
|TypeName|MarkISerializableTypesWithSerializable|  
|CheckId|CA2237|  
|类别|Microsoft.Usage|  
|是否重大更改|非重大更改|  
  
## <a name="cause"></a>原因  
 外部可见的类型实现<xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>接口和类型均未标有<xref:System.SerializableAttribute?displayProperty=fullName>属性。 规则将忽略其基类型不是可序列化的派生的类型。  
  
## <a name="rule-description"></a>规则说明  
 可以识别公共语言运行时为可序列化，类型必须标有<xref:System.SerializableAttribute>属性即使使用的类型通过实现一个自定义序列化例程<xref:System.Runtime.Serialization.ISerializable>接口。  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 若要修复与此规则的冲突，将应用<xref:System.SerializableAttribute>属性类型。  
  
## <a name="when-to-suppress-warnings"></a>何时禁止显示警告  
 因为它们必须是序列化，以在应用程序域之间正常工作，不要禁止显示此规则，异常类的警告。  
  
## <a name="example"></a>示例  
 下面的示例演示与该规则冲突的类型。 取消注释<xref:System.SerializableAttribute>属性以满足该规则的行。  
  
 [!code-vb[FxCop.Usage.MarkSerializable#1](../code-quality/codesnippet/VisualBasic/ca2237-mark-iserializable-types-with-serializableattribute_1.vb)]
 [!code-csharp[FxCop.Usage.MarkSerializable#1](../code-quality/codesnippet/CSharp/ca2237-mark-iserializable-types-with-serializableattribute_1.cs)]  
  
## <a name="related-rules"></a>相关的规则  
 [CA2236：对 ISerializable 类型调用基类方法](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)  
  
 [CA2240：正确实现 ISerializable](../code-quality/ca2240-implement-iserializable-correctly.md)  
  
 [CA2229：实现序列化构造函数](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2238：正确实现序列化方法](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
  
 [CA2235：标记所有不可序列化的字段](../code-quality/ca2235-mark-all-non-serializable-fields.md)  
  
 [CA2239：为可选字段提供反序列化方法](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
  
 [CA2120：保护序列化构造函数](../code-quality/ca2120-secure-serialization-constructors.md)