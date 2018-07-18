---
title: CA1006：不要将泛型类型嵌套在成员签名中
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotNestGenericTypesInMemberSignatures
- CA1006
helpviewer_keywords:
- CA1006
- DoNotNestGenericTypesInMemberSignatures
ms.assetid: dfc867bc-f4af-45d7-b071-db04a248f9fc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f6303cf96e3e8f6c4c0920336602cdbb76cc400a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31901157"
---
# <a name="ca1006-do-not-nest-generic-types-in-member-signatures"></a>CA1006：不要将泛型类型嵌套在成员签名中
|||
|-|-|
|TypeName|DoNotNestGenericTypesInMemberSignatures|
|CheckId|CA1006|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 外部可见成员有一个包含嵌套的类型参数的签名。

## <a name="rule-description"></a>规则说明
 嵌套类型参数是一个类型参数，也是一个泛型类型。 若要调用签名包含嵌套类型参数的成员，用户必须实例化一个泛型类型，并将此类型传递到另一个泛型类型的构造函数。 所需的过程和语法很复杂，应当避免。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，更改用于删除嵌套的类型参数的设计。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。 提供易于了解和使用的语法中的泛型可以减少需要了解并增加新库采用率的时间。

## <a name="example"></a>示例
 下面的示例演示与该规则冲突的方法以及调用该冲突方法所需的语法。

 [!code-vb[FxCop.Design.NestedGenerics#1](../code-quality/codesnippet/VisualBasic/ca1006-do-not-nest-generic-types-in-member-signatures_1.vb)]
 [!code-csharp[FxCop.Design.NestedGenerics#1](../code-quality/codesnippet/CSharp/ca1006-do-not-nest-generic-types-in-member-signatures_1.cs)]

## <a name="related-rules"></a>相关的规则
 [CA1005：避免泛型类型的参数过多](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010：集合应实现泛型接口](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000：不要在泛型类型中声明静态成员](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002：不要公开泛型列表](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1004：泛型方法应提供类型形参](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)

 [CA1003：使用泛型事件处理程序实例](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007：在适用处使用泛型](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>请参阅
 [泛型](/dotnet/csharp/programming-guide/generics/index)