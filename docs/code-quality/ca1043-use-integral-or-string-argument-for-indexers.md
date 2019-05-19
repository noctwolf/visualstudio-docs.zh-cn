---
title: CA1043:将整型或字符串参数用于索引器
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
helpviewer_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: ca381d88524535ad042b5bd3efda25f8cc350fa4
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842124"
---
# <a name="ca1043-use-integral-or-string-argument-for-indexers"></a>CA1043:将整型或字符串参数用于索引器

|||
|-|-|
|TypeName|UseIntegralOrStringArgumentForIndexers|
|CheckId|CA1043|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因

某个类型包含一个索引器，而不使用索引类型<xref:System.Int32?displayProperty=fullName>， <xref:System.Int64?displayProperty=fullName>， <xref:System.Object?displayProperty=fullName>，或<xref:System.String?displayProperty=fullName>。

默认情况下，此规则只看起来在公共和受保护类型，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

索引器，也就是说，索引属性，应为索引使用整数或字符串类型。 这些类型通常用于数据结构编制索引，并且提高库的可用性。 使用<xref:System.Object>类型应被限制为这种情况下，不能在设计时指定特定整型或字符串类型。 如果设计需要其他类型的索引，请重新考虑是否该类型表示逻辑数据存储区。 如果它不表示逻辑数据存储区，使用一种方法。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要解决此规则的冲突，更改为整数或字符串类型的索引，或使用一种方法，而不是索引器。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

禁止显示此规则仅在仔细考虑要使用非标准索引器后的警告。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```ini
dotnet_code_quality.ca1043.api_surface = private, internal
```

此类别 （设计） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。

## <a name="example"></a>示例

下面的示例演示使用的索引器<xref:System.Int32>索引。

[!code-csharp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CSharp/ca1043-use-integral-or-string-argument-for-indexers_1.cs)]
[!code-cpp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CPP/ca1043-use-integral-or-string-argument-for-indexers_1.cpp)]
[!code-vb[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/VisualBasic/ca1043-use-integral-or-string-argument-for-indexers_1.vb)]

## <a name="related-rules"></a>相关的规则

- [CA1023:索引器不应是多维](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)
- [CA1024： 在适用处在适用处使用属性](../code-quality/ca1024-use-properties-where-appropriate.md)