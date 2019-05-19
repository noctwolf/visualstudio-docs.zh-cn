---
title: CA1041:提供 ObsoleteAttribute 消息
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 354d1d2fe99fa55bba7f8a00bf3e9f760ff1dbaf
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842178"
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041:提供 ObsoleteAttribute 消息

|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|类别|Microsoft.Design|
|是否重大更改|非换行|

## <a name="cause"></a>原因

通过使用标记的类型或成员<xref:System.ObsoleteAttribute?displayProperty=fullName>属性不具有其<xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName>指定属性。

默认情况下，此规则仅查看外部可见的类型和成员，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

<xref:System.ObsoleteAttribute> 用于标记不推荐使用的库类型和成员。 库的使用者应避免使用任何类型或成员标记为已过时。 这是库的因为它可能不受支持并最终将从更高版本中删除。 类型或成员使用的标记时<xref:System.ObsoleteAttribute>进行编译，<xref:System.ObsoleteAttribute.Message%2A>显示特性的属性。 这将为用户提供有关已过时的类型或成员的信息。 此信息通常包括多长时间的已过时的类型或成员将支持的库设计器并使用首选的替代。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复此规则的冲突，请添加`message`参数<xref:System.ObsoleteAttribute>构造函数。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

因为不禁止显示此规则的警告<xref:System.ObsoleteAttribute.Message%2A>属性提供有关已过时的类型或成员的关键信息。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```ini
dotnet_code_quality.ca1041.api_surface = private, internal
```

此类别 （设计） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。

## <a name="example"></a>示例

下面的示例显示了过时的成员具有正确声明<xref:System.ObsoleteAttribute>。

[!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CPP/ca1041-provide-obsoleteattribute-message_1.cpp)]
[!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CSharp/ca1041-provide-obsoleteattribute-message_1.cs)]
[!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/VisualBasic/ca1041-provide-obsoleteattribute-message_1.vb)]

## <a name="see-also"></a>请参阅

- <xref:System.ObsoleteAttribute?displayProperty=fullName>