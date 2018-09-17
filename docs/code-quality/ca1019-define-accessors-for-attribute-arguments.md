---
title: CA1019：定义特性参数的访问器
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
helpviewer_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
ms.assetid: 197f2378-3c43-427e-80de-9ec25006c05c
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2e095c862edc5d7b68e1a6c55ada90a425b7e64f
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45550448"
---
# <a name="ca1019-define-accessors-for-attribute-arguments"></a>CA1019：定义特性参数的访问器

|||
|-|-|
|TypeName|DefineAccessorsForAttributeArguments|
|CheckId|CA1019|
|类别|Microsoft.Design|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 在其构造函数，属性定义不具有相应的属性的参数。

## <a name="rule-description"></a>规则说明
 特性可以定义强制自变量，在对目标应用该特性时必须指定这些自变量。 这些自变量也称为位置自变量，因为它们将作为位置参数提供给特性构造函数。 对于每一个强制自变量，特性还必须提供一个相应的只读属性，以便可以在执行时检索该自变量的值。 此规则检查每个构造函数参数，您已经定义了相应的属性。

 特性还可以定义可选实参，可选实参也称为命名实参。 这些变量按名称提供给特性构造函数，并且必须具有相应的读/写属性。

 对于必需和可选自变量时，相应的属性和构造函数参数应使用相同的名称但不同的大小写。 属性使用 Pascal 大小写，并且参数使用 camel 大小写。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请添加一个不具有每个构造函数参数的只读属性。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果不希望为可检索的强制参数的值，禁止显示此规则的警告。

## <a name="custom-attributes-example"></a>自定义特性的示例

下面的示例演示定义强制的 （位置） 参数的两个属性。 未正确定义该属性的第一个实现。 第二个实现正确。

[!code-csharp[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_1.cs)]
[!code-vb[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/VisualBasic/ca1019-define-accessors-for-attribute-arguments_1.vb)]

## <a name="positional-and-named-arguments"></a>位置和命名参数

位置和命名参数使它清楚地你哪些参数是必需的属性以及哪些参数是可选的库的使用者。

下面的示例显示了具有位置和命名参数的属性的实现：

[!code-csharp[FxCop.Design.AttributeAccessorsNamed#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_2.cs)]

下面的示例演示如何将自定义特性应用于两个属性：

[!code-csharp[FxCop.Design.AttributeAccessorsNamedApplied#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_3.cs)]

## <a name="related-rules"></a>相关的规则
 [CA1813：避免使用未密封的特性](../code-quality/ca1813-avoid-unsealed-attributes.md)

## <a name="see-also"></a>请参阅
 [特性](/dotnet/standard/design-guidelines/attributes)