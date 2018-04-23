---
title: CA1041：提供 ObsoleteAttribute 消息
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 94a8204b2b19ae32fb8eb22438d747f4b4e0cf6c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041：提供 ObsoleteAttribute 消息
|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|类别|Microsoft.Design|
|是否重大更改|非重大|

## <a name="cause"></a>原因
 使用标记类型或成员<xref:System.ObsoleteAttribute?displayProperty=fullName>属性不具有其<xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName>指定属性。

## <a name="rule-description"></a>规则说明
 <xref:System.ObsoleteAttribute> 用于将标记不推荐使用的库类型和成员。 库使用者应避免任何类型或成员标记为过时的使用。 这是因为它可能不受支持，最终将从更高版本的库中删除。 通过使用类型或成员的标记时<xref:System.ObsoleteAttribute>编译后，<xref:System.ObsoleteAttribute.Message%2A>显示的属性的属性。 这将为用户提供有关已过时的类型或成员的信息。 此信息通常包括多长时间已过时的类型或成员将受库设计器和首选的替换使用。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，将添加`message`参数<xref:System.ObsoleteAttribute>构造函数。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 因为不禁止显示此规则的警告<xref:System.ObsoleteAttribute.Message%2A>属性提供有关已过时的类型或成员的关键信息。

## <a name="example"></a>示例
 下面的示例演示过时的成员具有正确声明<xref:System.ObsoleteAttribute>。

 [!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CPP/ca1041-provide-obsoleteattribute-message_1.cpp)]
 [!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CSharp/ca1041-provide-obsoleteattribute-message_1.cs)]
 [!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/VisualBasic/ca1041-provide-obsoleteattribute-message_1.vb)]

## <a name="see-also"></a>请参阅
 <xref:System.ObsoleteAttribute?displayProperty=fullName>