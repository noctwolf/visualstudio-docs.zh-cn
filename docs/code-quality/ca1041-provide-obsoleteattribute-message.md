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
ms.openlocfilehash: a0545503b80e2f256593012e06cdf7ccd8b3b5b1
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547640"
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041:提供 ObsoleteAttribute 消息

|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|类别|Microsoft.Design|
|是否重大更改|不间断|

## <a name="cause"></a>原因

使用<xref:System.ObsoleteAttribute?displayProperty=fullName> 未<xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName>指定属性的特性标记类型或成员。

默认情况下, 此规则仅查看外部可见类型和成员, 但这是[可配置](#configurability)的。

## <a name="rule-description"></a>规则说明

<xref:System.ObsoleteAttribute>用于标记不推荐使用的库类型和成员。 库使用者应避免使用任何标记为过时的类型或成员。 这是因为它可能不受支持, 最终将从库的更高版本中删除。 在编译使用<xref:System.ObsoleteAttribute>标记的类型或成员时<xref:System.ObsoleteAttribute.Message%2A> , 将显示该特性的属性。 这将为用户提供有关已过时的类型或成员的信息。 此信息通常包括库设计器支持过时的类型或成员的时间, 以及要使用的首选替换。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复与此规则的冲突, 请`message`将参数添加<xref:System.ObsoleteAttribute>到构造函数。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

请勿禁止显示此规则发出的警告, <xref:System.ObsoleteAttribute.Message%2A>因为属性提供有关已过时的类型或成员的重要信息。

## <a name="configurability"></a>配置

如果从[FxCop 分析器](install-fxcop-analyzers.md)(而不是传统分析) 运行此规则, 则可以根据其可访问性, 将基本代码的哪些部分配置为在上运行此规则。 例如, 若要指定规则只应针对非公共 API 图面运行, 请在项目中的 editorconfig 文件中添加以下键/值对:

```ini
dotnet_code_quality.ca1041.api_surface = private, internal
```

您可以为此规则、所有规则或此类别中的所有规则 (设计) 配置此选项。 有关详细信息, 请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。

## <a name="example"></a>示例

下面的示例显示一个已正确声明<xref:System.ObsoleteAttribute>的过时成员。

[!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CPP/ca1041-provide-obsoleteattribute-message_1.cpp)]
[!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CSharp/ca1041-provide-obsoleteattribute-message_1.cs)]
[!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/VisualBasic/ca1041-provide-obsoleteattribute-message_1.vb)]

## <a name="see-also"></a>请参阅

- <xref:System.ObsoleteAttribute?displayProperty=fullName>