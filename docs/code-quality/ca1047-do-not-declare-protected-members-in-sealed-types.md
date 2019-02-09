---
title: CA1047:不要在密封类型中声明受保护的成员
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotDeclareProtectedMembersInSealedTypes
- CA1047
helpviewer_keywords:
- CA1047
- DoNotDeclareProtectedMembersInSealedTypes
ms.assetid: 829033b5-a9d8-4f26-a719-45494c9dd035
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: c138c05d755b05275755f96776764604997cbbcd
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55921544"
---
# <a name="ca1047-do-not-declare-protected-members-in-sealed-types"></a>CA1047:不要在密封类型中声明受保护的成员

|||
|-|-|
|TypeName|DoNotDeclareProtectedMembersInSealedTypes|
|CheckId|CA1047|
|类别|Microsoft.Design|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 公共类型是`sealed`(`NotInheritable`在 Visual basic 中) 和声明受保护的成员或受保护的嵌套的类型。 此规则不会报告的冲突<xref:System.Object.Finalize%2A>必须遵循此模式的方法。

## <a name="rule-description"></a>规则说明
 类型声明受保护的成员，使继承类型可以访问或重写该成员。 根据定义，不能继承密封类型，不能调用这意味着，受保护的密封的类型上的方法。

 C# 编译器会发出此错误的警告。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复该规则的冲突，请将该成员的访问级别更改为私有的或创建该类型可继承。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。 在其当前状态使类型可能会导致维护问题，它不提供任何权益。

## <a name="example"></a>示例
 下面的示例显示了与此规则冲突的类型。

 [!code-vb[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/VisualBasic/ca1047-do-not-declare-protected-members-in-sealed-types_1.vb)]
 [!code-csharp[FxCop.Design.SealedNoProtected#1](../code-quality/codesnippet/CSharp/ca1047-do-not-declare-protected-members-in-sealed-types_1.cs)]