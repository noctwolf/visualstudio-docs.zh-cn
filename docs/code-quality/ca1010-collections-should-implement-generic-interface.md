---
title: CA1010:集合应实现泛型接口
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
helpviewer_keywords:
- CA1010
- CollectionsShouldImplementGenericInterface
ms.assetid: c7d7126f-fa70-40be-8f93-3243e1760dc5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c71912fdd70226e1b4be3c14be7c4e0bac26259d
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57871897"
---
# <a name="ca1010-collections-should-implement-generic-interface"></a>CA1010:集合应实现泛型接口

|||
|-|-|
|TypeName|CollectionsShouldImplementGenericInterface|
|CheckId|CA1010|
|类别|Microsoft.Design|
|是否重大更改|非换行|

## <a name="cause"></a>原因

一个类型实现<xref:System.Collections.IEnumerable?displayProperty=fullName>接口，但不实现<xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>接口，并且包含程序集的目标.NET。 此规则会忽略类型实现的<xref:System.Collections.IDictionary?displayProperty=fullName>。

默认情况下，此规则只看起来在外部可见的类型，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

若要扩大集合的用途，应实现某个泛型集合接口。 然后可以使用集合来填充泛型集合类型，如下所示：

- <xref:System.Collections.Generic.List%601?displayProperty=fullName>
- <xref:System.Collections.Generic.Queue%601?displayProperty=fullName>
- <xref:System.Collections.Generic.Stack%601?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>如何解决冲突

若要解决此规则的冲突，实现以下泛型集合接口之一：

- <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>
- <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName>
- <xref:System.Collections.Generic.IList%601?displayProperty=fullName>

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

则可以安全地禁止显示此规则; 的警告但是，该集合的使用将更多限制。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```
dotnet_code_quality.ca1010.api_surface = private, internal
```

此类别 （设计） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。

## <a name="example-violation"></a>冲突的示例

下面的示例演示派生自非泛型类 （引用类型）`CollectionBase`类，与此规则冲突。

[!code-csharp[FxCop.Design.CollectionsGenericViolation#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_1.cs)]

若要解决此规则的冲突，请执行以下操作：

- 实现泛型接口。
- 将基类更改为已实现了这两个泛型和非泛型接口，如类型`Collection<T>`类。

## <a name="fix-by-base-class-change"></a>修复由基类更改

下面的示例通过从非泛型更改集合的基类中修复了冲突`CollectionBase`泛型类`Collection<T>`(`Collection(Of T)`在 Visual Basic 中) 类。

[!code-csharp[FxCop.Design.CollectionsGenericBase#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_2.cs)]

更改已发布的类的基类被视为对现有使用者的重大更改。

## <a name="fix-by-interface-implementation"></a>通过接口实现来解决

下面的示例通过实现这些泛型接口中修复了冲突： `IEnumerable<T>`， `ICollection<T>`，并`IList<T>`(`IEnumerable(Of T)`， `ICollection(Of T)`，并`IList(Of T)`在 Visual Basic 中)。

[!code-csharp[FxCop.Design.CollectionsGenericInterface#1](../code-quality/codesnippet/CSharp/ca1010-collections-should-implement-generic-interface_3.cs)]

## <a name="related-rules"></a>相关的规则

- [CA1005:避免泛型类型参数过多](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)
- [CA1000:不要在泛型类型中声明静态成员](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)
- [CA1002:不要公开泛型列表](../code-quality/ca1002-do-not-expose-generic-lists.md)
- [CA1006:不要将嵌套在成员签名中的泛型类型](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)
- [CA1004:泛型方法应提供类型参数](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)
- [CA1003:使用泛型事件处理程序实例](../code-quality/ca1003-use-generic-event-handler-instances.md)
- [CA1007： 在适用处在适用处使用泛型](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>请参阅

- [泛型](/dotnet/csharp/programming-guide/generics/index)