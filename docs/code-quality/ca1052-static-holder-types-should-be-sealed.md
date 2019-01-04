---
title: CA1052:应密封静态容器类型
ms.date: 11/09/2018
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- StaticHolderTypesShouldBeSealed
- CA1052
helpviewer_keywords:
- CA1052
- StaticHolderTypesShouldBeSealed
ms.assetid: 51a3165d-781e-4a55-aa0d-ea25fee7d4f2
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 0ec090fd11c122699bafb3d72ca1eeab13ecb830
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53825940"
---
# <a name="ca1052-static-holder-types-should-be-sealed"></a>CA1052:应密封静态容器类型

|||
|-|-|
|TypeName|StaticHolderTypesShouldBeSealed|
|CheckId|CA1052|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因

公共或受保护，非抽象类型仅包含静态成员和不使用声明[密封](/dotnet/csharp/language-reference/keywords/sealed)([NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)) 修饰符。

## <a name="rule-description"></a>规则说明

规则 CA1052 假定只包含静态成员的类型未设计为继承，因为该类型不提供可以在派生类型中重写任何功能。 不希望被继承的类型应标记为`sealed`或`NotInheritable`修饰符来禁止其用作基类型。 此规则不会激发为抽象类。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复此规则的冲突，请将标记为类型`sealed`或`NotInheritable`。 如果您的目标.NET Framework 2.0 或更高版本，更好的方法是将类型标记为`static`或`Shared`。 以这种方式，您无需专用的构造函数，以防止此类创建声明。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

仅当类型能被继承，禁止显示此规则的警告。 如果没有`sealed`或`NotInheritable`修饰符，则表明该类型用作基类型。

## <a name="example-of-a-violation"></a>冲突的示例

下面的示例显示了违反了此规则的类型。

[!code-csharp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_1.cs)]
[!code-vb[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/VisualBasic/ca1052-static-holder-types-should-be-sealed_1.vb)]
[!code-cpp[FxCop.Design.StaticMembers#1](../code-quality/codesnippet/CPP/ca1052-static-holder-types-should-be-sealed_1.cpp)]

## <a name="fix-with-the-static-modifier"></a>修复使用静态修饰符

下面的示例演示如何通过将标记的类型来修复该规则的冲突`static`修饰符C#。

[!code-csharp[FxCop.Design.StaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1052-static-holder-types-should-be-sealed_2.cs)]

## <a name="related-rules"></a>相关的规则

[CA1053:静态容器类型不应具有构造函数](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)