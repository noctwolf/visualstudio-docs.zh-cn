---
title: CA1048:不要在密封类型中声明虚拟成员
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
helpviewer_keywords:
- DoNotDeclareVirtualMembersInSealedTypes
- CA1048
ms.assetid: 5dcf4a30-6f98-48a8-b8cc-7b89ea757262
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 026a1b2cbcd75bd2f39cc6f169b0a1a2feddb258
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53872877"
---
# <a name="ca1048-do-not-declare-virtual-members-in-sealed-types"></a>CA1048:不要在密封类型中声明虚拟成员

|||
|-|-|
|TypeName|DoNotDeclareVirtualMembersInSealedTypes|
|CheckId|CA1048|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 公共类型密封的将方法同时声明`virtual`(`Overridable`在 Visual Basic 中) 并不是最终。 此规则不会报告冲突，委托类型，必须遵循此模式。

## <a name="rule-description"></a>规则说明
 类型将方法声明为虚方法，使继承类型可以重写虚方法的实现。 根据定义，不能继承密封类型，使得在密封类型上的虚拟方法没有意义。

 Visual Basic 和 C# 编译器不允许违反此规则的类型。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，使该方法成为非虚方法或使该类型可继承。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。 在其当前状态使类型可能会导致维护问题，它不提供任何权益。

## <a name="example"></a>示例
 下面的示例显示了与此规则冲突的类型。

 [!code-cpp[FxCop.Design.SealedVirtual#1](../code-quality/codesnippet/CPP/ca1048-do-not-declare-virtual-members-in-sealed-types_1.cpp)]