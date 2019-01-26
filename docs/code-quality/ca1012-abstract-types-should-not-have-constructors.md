---
title: CA1012:抽象类型不应具有构造函数
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- AbstractTypesShouldNotHaveConstructors
- CA1012
helpviewer_keywords:
- CA1012
ms.assetid: 09f458ac-dd88-4cd7-a47f-4106c1e80ece
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: dd35cd7b084deb34b23b49ebc04517733c5478c9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55006772"
---
# <a name="ca1012-abstract-types-should-not-have-constructors"></a>CA1012:抽象类型不应具有构造函数

|||
|-|-|
|TypeName|AbstractTypesShouldNotHaveConstructors|
|CheckId|CA1012|
|类别|Microsoft.Design|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 公共类型是抽象的具有公共构造函数。

## <a name="rule-description"></a>规则说明
 抽象类型的构造函数只能由派生类型调用。 由于公共构造函数用于创建类型的实例，但无法为抽象类型创建实例，因此具有公共构造函数的抽象类在设计上是错误的。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，使受保护的构造函数或未声明为抽象类型。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。 抽象类型具有公共构造函数。

## <a name="example"></a>示例
 下面的示例包含与此规则冲突的抽象类。

 [!code-vb[FxCop.Design.AbstractTypeBad#1](../code-quality/codesnippet/VisualBasic/ca1012-abstract-types-should-not-have-constructors_1.vb)]
 [!code-csharp[FxCop.Design.AbstractTypeBad#1](../code-quality/codesnippet/CSharp/ca1012-abstract-types-should-not-have-constructors_1.cs)]

## <a name="example"></a>示例
 下面的示例通过从构造函数的可访问性更改修复了前面的冲突`public`到`protected`。

 [!code-csharp[FxCop.Design.AbstractTypeGood#1](../code-quality/codesnippet/CSharp/ca1012-abstract-types-should-not-have-constructors_2.cs)]
 [!code-vb[FxCop.Design.AbstractTypeGood#1](../code-quality/codesnippet/VisualBasic/ca1012-abstract-types-should-not-have-constructors_2.vb)]