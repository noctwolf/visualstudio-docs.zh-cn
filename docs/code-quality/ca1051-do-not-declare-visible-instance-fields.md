---
title: CA1051:不要声明可见实例字段
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fd4783f6327061da0ce522cc02082289cdee3d39
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55938086"
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051:不要声明可见实例字段

|||
|-|-|
|TypeName|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 外部可见的类型具有一个外部可见实例字段。

## <a name="rule-description"></a>规则说明
 字段的主要用途应是作为实现的详细信息。 字段应`private`或`internal`和应通过使用属性公开。 很容易访问的属性是要访问的字段和属性访问器中的代码可以更改随着类型的功能扩展，而不会引入重大更改。 只需返回私有或内部字段的值的属性进行了优化来执行与相媲美访问字段;很少的性能提升是通过属性与外部可见字段的使用相关联。

 外部可见指`public`， `protected`，并`protected internal`(`Public`， `Protected`，并`Protected Friend`在 Visual Basic 中) 可访问性级别。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，使字段`private`或`internal`并将其公开使用的外部可见的属性。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。 外部可见字段不提供对属性不可用的任何权益。 此外，不能由保护公共字段[链接要求](/dotnet/framework/misc/link-demands)。 请参阅[CA2112:受保护的类型不应公开字段](../code-quality/ca2112-secured-types-should-not-expose-fields.md)。

## <a name="example"></a>示例
 下面的示例演示一种类型 (`BadPublicInstanceFields`) 这违反了此规则。 `GoodPublicInstanceFields` 显示了更正后的代码。

 [!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../code-quality/codesnippet/CSharp/ca1051-do-not-declare-visible-instance-fields_1.cs)]

## <a name="related-rules"></a>相关的规则
 [CA2112:受保护的类型不应公开字段](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## <a name="see-also"></a>请参阅
 [链接需求](/dotnet/framework/misc/link-demands)