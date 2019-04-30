---
title: CA1003:使用泛型事件处理程序实例
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UseGenericEventHandlerInstances
- CA1003
helpviewer_keywords:
- CA1003
- UseGenericEventHandlerInstances
ms.assetid: 402101b6-555d-4cf7-b223-1d9fdfaaf1cd
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: eff7b4b880526909c293e16aa32ae7045bcdf297
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62780029"
---
# <a name="ca1003-use-generic-event-handler-instances"></a>CA1003:使用泛型事件处理程序实例

|||
|-|-|
|TypeName|UseGenericEventHandlerInstances|
|CheckId|CA1003|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因

一种类型包含一个委托，它返回 void，其签名包含两个参数 （一个的对象的第一个和第二个是分配给 EventArgs 的类型） 和包含程序集的目标.NET。

默认情况下，此规则只看起来在外部可见的类型，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

在之前.NET，以便将自定义信息传递给事件处理程序，一个新委托，必须指定派生自的类声明<xref:System.EventArgs?displayProperty=fullName>类。 这是不能再在.NET 中，则返回 true。 引入的.NET Framework<xref:System.EventHandler%601?displayProperty=fullName>委托、 允许的任何类都派生自的泛型委托<xref:System.EventArgs>来与事件处理程序一起使用。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要解决此规则的冲突，移除了该委托，并将其用途为通过使用<xref:System.EventHandler%601?displayProperty=fullName>委托。

如果委托由 Visual Basic 编译器自动生成，请更改要使用的事件声明的语法<xref:System.EventHandler%601?displayProperty=fullName>委托。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不禁止显示此规则发出的警告。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```
dotnet_code_quality.ca1003.api_surface = private, internal
```

此类别 （设计） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。

## <a name="example"></a>示例

下面的示例显示了一个委托，它违反了此规则。 在 Visual Basic 示例中，注释说明了如何修改示例以满足该规则。 对于 C# 示例，以下是一个示例显示修改后的代码。

[!code-vb[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/VisualBasic/ca1003-use-generic-event-handler-instances_1.vb)]
[!code-csharp[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_1.cs)]

下面的代码段从上一示例中，这样可满足该规则中删除与委托声明。 它将替换中的使用该`ClassThatRaisesEvent`并`ClassThatHandlesEvent`方法通过使用<xref:System.EventHandler%601?displayProperty=fullName>委托。

[!code-csharp[FxCop.Design.GenericEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_2.cs)]

## <a name="related-rules"></a>相关的规则

- [CA1005:避免泛型类型参数过多](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)
- [CA1010:集合应实现泛型接口](../code-quality/ca1010-collections-should-implement-generic-interface.md)
- [CA1000:不要在泛型类型中声明静态成员](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)
- [CA1002:不要公开泛型列表](../code-quality/ca1002-do-not-expose-generic-lists.md)
- [CA1006:不要将嵌套在成员签名中的泛型类型](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)
- [CA1004:泛型方法应提供类型参数](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)
- [CA1007： 在适用处在适用处使用泛型](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>请参阅

- [泛型](/dotnet/csharp/programming-guide/generics/index)