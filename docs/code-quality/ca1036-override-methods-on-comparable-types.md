---
title: CA1036:重写可比较类型中的方法
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1036
- OverrideMethodsOnComparableTypes
helpviewer_keywords:
- OverrideMethodsOnComparableTypes
- CA1036
ms.assetid: 2329f844-4cb8-426d-bee2-cd065d1346d0
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bd87e75134494ef928708e64015f413bc85878c8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54980682"
---
# <a name="ca1036-override-methods-on-comparable-types"></a>CA1036:重写可比较类型中的方法

|||
|-|-|
|TypeName|OverrideMethodsOnComparableTypes|
|CheckId|CA1036|
|类别|Microsoft.Design|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 公共或受保护类型实现<xref:System.IComparable?displayProperty=fullName>接口，并不会覆盖<xref:System.Object.Equals%2A?displayProperty=fullName>或不太不会重载相等、 不等，特定于语言的运算符-或更高的比。 如果该类型继承接口的实现，该规则不报告冲突。

## <a name="rule-description"></a>规则说明

定义自定义排序顺序的类型可实现<xref:System.IComparable>接口。 <xref:System.IComparable.CompareTo%2A>方法返回一个整数值，指示该类型的两个实例的正确的排序顺序。 此规则可确定排序顺序设置的类型。 设置排序顺序意味着普通意义上的相等、 不等，更少的和大于-比不适用。 提供的实现时<xref:System.IComparable>，通常必须还重写<xref:System.Object.Equals%2A>，以便它将返回值与相一致<xref:System.IComparable.CompareTo%2A>。 如果重写<xref:System.Object.Equals%2A>进行编码和支持的运算符重载的语言，您还应提供与一致的运算符<xref:System.Object.Equals%2A>。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复此规则的冲突，请重写<xref:System.Object.Equals%2A>。 如果您的编程语言支持运算符重载，提供以下运算符：

- op_Equality

- op_Inequality

- op_LessThan

- op_GreaterThan

在 C# 中，用来表示这些运算符的令牌如下所示：

```csharp
==
!=
<
>
```

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它可以安全地禁止显示 CA1036 冲突是由缺少运算符和您的编程语言不支持运算符重载，而是使用 Visual Basic 这种情况的规则的警告。 它也是安全地禁止显示此规则的警告，而不 op_Equality 如果你确定实现了运算符的应用程序上下文中不难理解它触发上相等运算符时。 但是，您应始终通过 op_Equality 和 = = 运算符，如果重写 Object.Equals。

## <a name="example"></a>示例
 下面的示例包含正确实现的类型<xref:System.IComparable>。 代码注释标识满足与相关的各种规则的方法<xref:System.Object.Equals%2A>和<xref:System.IComparable>接口。

 [!code-csharp[FxCop.Design.IComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_1.cs)]

## <a name="example"></a>示例
 下面的应用程序测试的行为<xref:System.IComparable>前面所示的实现。

 [!code-csharp[FxCop.Design.TestIComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_2.cs)]

## <a name="see-also"></a>请参阅

- <xref:System.IComparable?displayProperty=fullName>
- <xref:System.Object.Equals%2A?displayProperty=fullName>
- [相等运算符](/dotnet/standard/design-guidelines/equality-operators)