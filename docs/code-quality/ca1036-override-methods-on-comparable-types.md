---
title: CA1036:重写可比较类型中的方法
ms.date: 03/11/2019
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
ms.openlocfilehash: 12b00c202373310b04021a46e74af2af7e10d535
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57868867"
---
# <a name="ca1036-override-methods-on-comparable-types"></a>CA1036:重写可比较类型中的方法

|||
|-|-|
|TypeName|OverrideMethodsOnComparableTypes|
|CheckId|CA1036|
|类别|Microsoft.Design|
|是否重大更改|非换行|

## <a name="cause"></a>原因

某个类型实现<xref:System.IComparable?displayProperty=fullName>接口，并不会覆盖<xref:System.Object.Equals%2A?displayProperty=fullName>或不太不会重载相等、 不等，特定于语言的运算符-或更高的比。 如果该类型继承接口的实现，该规则不报告冲突。

默认情况下，此规则只看起来在公共和受保护类型，但这是[可配置](#configurability)。

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

它可以安全地禁止显示 CA1036 冲突是由缺少运算符和您的编程语言不支持运算符重载，而是使用 Visual Basic 这种情况的规则的警告。 如果您确定，实现运算符没有意义，在应用程序上下文中，它也是安全地禁止显示此规则的警告，它将引发 op_Equality 以外的相等运算符时。 但是，您应始终覆盖 op_Equality 和 = = 运算符，如果重写<xref:System.Object.Equals%2A?displayProperty=nameWithType>。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```
dotnet_code_quality.ca1036.api_surface = private, internal
```

此类别 （设计） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。

## <a name="examples"></a>示例

下面的代码包含正确实现的类型<xref:System.IComparable>。 代码注释标识满足与相关的各种规则的方法<xref:System.Object.Equals%2A>和<xref:System.IComparable>接口。

[!code-csharp[FxCop.Design.IComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_1.cs)]

下面的应用程序代码测试的行为<xref:System.IComparable>前面所示的实现。

[!code-csharp[FxCop.Design.TestIComparable#1](../code-quality/codesnippet/CSharp/ca1036-override-methods-on-comparable-types_2.cs)]

## <a name="see-also"></a>请参阅

- <xref:System.IComparable?displayProperty=fullName>
- <xref:System.Object.Equals%2A?displayProperty=fullName>
- [相等运算符](/dotnet/standard/design-guidelines/equality-operators)