---
title: CA1002：不要公开泛型列表
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotExposeGenericLists
- CA1002
helpviewer_keywords:
- CA1002
- DoNotExposeGenericLists
ms.assetid: 5caac810-1a79-47df-a27b-c46c5040bf34
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 24646a2ac02f4ec8974c1806ca761b2e7a5af5a0
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49923950"
---
# <a name="ca1002-do-not-expose-generic-lists"></a>CA1002：不要公开泛型列表

|||
|-|-|
|TypeName|DoNotExposeGenericLists|
|CheckId|CA1002|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 某个类型包含外部可见成员<xref:System.Collections.Generic.List%601?displayProperty=fullName>类型，将返回<xref:System.Collections.Generic.List%601?displayProperty=fullName>类型或其签名包含<xref:System.Collections.Generic.List%601?displayProperty=fullName>参数。

## <a name="rule-description"></a>规则说明
 <xref:System.Collections.Generic.List%601?displayProperty=fullName> 是专为性能和不继承的泛型集合。 <xref:System.Collections.Generic.List%601?displayProperty=fullName> 不包含虚拟成员，从而使更轻松地更改继承的类的行为。 下面的泛型集合用于继承，因此而不是不应公开<xref:System.Collections.Generic.List%601?displayProperty=fullName>。

- <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>

- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>

- <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请更改<xref:System.Collections.Generic.List%601?displayProperty=fullName>类型设置为一个针对继承设计的泛型集合。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 除非引发此警告的程序集不应为可重用的库，否则不要禁止显示此规则的警告。 例如，它可以放心地取消显示此警告在性能优化应用程序中的泛型列表使用获得性能优势，是。

## <a name="related-rules"></a>相关的规则
 [CA1005：避免泛型类型的参数过多](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010：集合应实现泛型接口](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000：不要在泛型类型中声明静态成员](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1006：不要将泛型类型嵌套在成员签名中](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1004：泛型方法应提供类型形参](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003：使用泛型事件处理程序实例](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007：在适用处使用泛型](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>请参阅
 [泛型](/dotnet/csharp/programming-guide/generics/index)