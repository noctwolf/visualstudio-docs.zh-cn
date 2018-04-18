---
title: CA1038： 枚举器应为强类型 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- EnumeratorsShouldBeStronglyTyped
- CA1038
helpviewer_keywords:
- EnumeratorsShouldBeStronglyTyped
- CA1038
ms.assetid: 8919f526-d487-42a4-87dc-2b2ee25260c4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 01b194864f559ff095d8727ff11a4906377aa482
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="ca1038-enumerators-should-be-strongly-typed"></a>CA1038：枚举数应强类型化
|||  
|-|-|  
|TypeName|EnumeratorsShouldBeStronglyTyped|  
|CheckId|CA1038|  
|类别|Microsoft.Design|  
|是否重大更改|重大|  
  
## <a name="cause"></a>原因  
 公共或受保护类型实现<xref:System.Collections.IEnumerator?displayProperty=fullName>但未提供的强类型的版本<xref:System.Collections.IEnumerator.Current%2A?displayProperty=fullName>属性。 从以下类型派生的类型不受此规则：  
  
-   <xref:System.Collections.CollectionBase?displayProperty=fullName>  
  
-   <xref:System.Collections.DictionaryBase?displayProperty=fullName>  
  
-   <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>  
  
## <a name="rule-description"></a>规则说明  
 此规则要求<xref:System.Collections.IEnumerator>实现还提供强类型的版本以<xref:System.Collections.IEnumerator.Current%2A>属性，以便用户无需在界面中使用提供的功能时，强制转换为强类型的返回值。 此规则假定该类型实现<xref:System.Collections.IEnumerator>包含强于类型的实例集合<xref:System.Object>。  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 若要修复与此规则的冲突，请显式实现接口属性 (将其声明为`IEnumerator.Current`)。 添加的属性，声明为公共的强类型的版本`Current`，并将它返回强类型的对象。  
  
## <a name="when-to-suppress-warnings"></a>何时禁止显示警告  
 禁止显示此规则的警告，当您实现与基于对象的集合，如二进制树一起使用的基于对象的枚举数。 扩展新集合的类型将定义强类型化枚举器，并公开强类型的属性。  
  
## <a name="example"></a>示例  
 下面的示例演示实现强类型化的正确方法<xref:System.Collections.IEnumerator>类型。  
  
 [!code-csharp[FxCop.Design.IEnumeratorStrongTypes#1](../code-quality/codesnippet/CSharp/ca1038-enumerators-should-be-strongly-typed_1.cs)]  
  
## <a name="related-rules"></a>相关的规则  
 [CA1035：ICollection 实现含有强类型成员](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)  
  
 [CA1039：列表已强类型化](../code-quality/ca1039-lists-are-strongly-typed.md)  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Collections.IEnumerator?displayProperty=fullName>   
 <xref:System.Collections.CollectionBase?displayProperty=fullName>   
 <xref:System.Collections.DictionaryBase?displayProperty=fullName>   
 <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>