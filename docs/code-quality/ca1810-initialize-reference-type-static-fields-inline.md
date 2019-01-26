---
title: CA1810:以内联方式初始化引用类型的静态字段
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- InitializeReferenceTypeStaticFieldsInline
- CA1810
helpviewer_keywords:
- InitializeReferenceTypeStaticFieldsInline
- CA1810
ms.assetid: e9693118-a914-4efb-9550-ec659d8d97d2
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 42877ea2b3b42f0fc9bed5c88a6809ba31cab3e2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54996917"
---
# <a name="ca1810-initialize-reference-type-static-fields-inline"></a>CA1810:以内联方式初始化引用类型的静态字段

|||
|-|-|
|TypeName|InitializeReferenceTypeStaticFieldsInline|
|CheckId|CA1810|
|类别|Microsoft.Performance|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 引用类型声明显式静态构造函数。

## <a name="rule-description"></a>规则说明
 当一个类型声明显式静态构造函数时，实时 (JIT) 编译器会向该类型的每个静态方法和实例构造函数中添加一项检查，以确保之前已调用该静态构造函数。 当访问任何静态成员或创建类型的实例时，将触发静态初始化。 但是，如果声明类型的变量，但不是使用它，可以是重要信息： 如果在初始化更改全局状态的则不会触发静态初始化。

 当所有静态数据初始化的内联且未声明显式静态构造函数时，Microsoft 中间语言 (MSIL) 编译器添加`beforefieldinit`标志和隐式静态构造函数，这将初始化为 MSIL 类型的静态数据定义。 当 JIT 编译器遇到`beforefieldinit`标志，大多数情况下不会添加静态构造函数检查。 静态初始化保证访问任何静态字段之前，但不是调用静态方法或实例构造函数之前的某个时刻发生。 请注意，静态初始化可以任何时候声明类型的变量后发生。

 静态构造函数检查会降低性能。 通常使用静态构造函数仅用于初始化静态字段，只需确保该静态初始化的情况下在静态字段在首次访问之前发生。 `beforefieldinit`行为是适用于这些和大多数其他类型。 静态初始化会影响全局状态和以下项之一为 true 时才不合适：

- 对全局状态的影响很高，如果不使用该类型不需要。

- 而无需访问类型的任何静态字段，可以访问全局状态的副作用。

## <a name="how-to-fix-violations"></a>如何解决冲突
 要修复与该规则的冲突，请在声明它时初始化所有静态数据并移除静态构造函数。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 则可以安全地禁止显示此规则的警告，如果性能不是一个问题;或如果全局状态更改而引起静态初始化的开销都很大，或必须能保证会出现在调用类型的静态方法或创建类型的实例。

## <a name="example"></a>示例

下面的示例演示一种类型， `StaticConstructor`，这违反了规则和一个类型， `NoStaticConstructor`，静态构造函数替换内联初始化，以满足该规则。

[!code-csharp[FxCop.Performance.RefTypeStaticCtor#1](../code-quality/codesnippet/CSharp/ca1810-initialize-reference-type-static-fields-inline_1.cs)]
[!code-vb[FxCop.Performance.RefTypeStaticCtor#1](../code-quality/codesnippet/VisualBasic/ca1810-initialize-reference-type-static-fields-inline_1.vb)]

请注意添加`beforefieldinit`标志的 MSIL 定义`NoStaticConstructor`类。

```
.class public auto ansi StaticConstructor
extends [mscorlib]System.Object
{
} // end of class StaticConstructor

.class public auto ansi beforefieldinit NoStaticConstructor
extends [mscorlib]System.Object
{
} // end of class NoStaticConstructor
```

## <a name="related-rules"></a>相关的规则

- [CA2207:值类型的静态字段以内联方式初始化](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)