---
title: CA2234:传递 System.Uri 对象，而不传递字符串
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- PassSystemUriObjectsInsteadOfStrings
- CA2234
helpviewer_keywords:
- CA2234
- PassSystemUriObjectsInsteadOfStrings
ms.assetid: 14616b37-74c4-4286-b051-115d00aceb5f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 97b73793d0c473727960dbde8fe32fc584ff6dd5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541691"
---
# <a name="ca2234-pass-systemuri-objects-instead-of-strings"></a>CA2234:传递 System.Uri 对象，而不传递字符串

|||
|-|-|
|TypeName|PassSystemUriObjectsInsteadOfStrings|
|CheckId|CA2234|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因

调用具有其名称包含"uri"、"Uri"、"urn"、"Urn"、"url"或"Url"的字符串参数的方法，但该方法的声明类型包含具有相应的方法重载<xref:System.Uri?displayProperty=fullName>参数。

默认情况下，此规则仅查看外部可见方法和类型，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

参数名称拆分为基于驼峰式大小写约定的标记，然后检查每个令牌，以确定它是否等于"uri"、"Uri"、"urn"、"Urn"、"url"或"Url"。 如果没有匹配项，则假定该参数表示统一资源标识符 (URI)。 URI 的字符串表示形式容易导致分析和编码错误，并且可造成安全漏洞。 <xref:System.Uri>类以安全的方式提供这些服务。 在两个唯一的表示形式的 URI 方面的差别的重载之间存在一个选择时，用户应选择的重载的<xref:System.Uri>参数。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复此规则的冲突，请调用的重载的<xref:System.Uri>参数。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

它可以安全地禁止显示此规则的警告，如果字符串参数不表示一个 URI。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```
dotnet_code_quality.ca2234.api_surface = private, internal
```

此类别 （用法） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。

## <a name="example"></a>示例

下面的示例演示一种方法， `ErrorProne`，这违反了规则和方法， `SaferWay`，，正确调用<xref:System.Uri>重载：

[!code-vb[FxCop.Usage.PassUri#1](../code-quality/codesnippet/VisualBasic/ca2234-pass-system-uri-objects-instead-of-strings_1.vb)]
[!code-cpp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CPP/ca2234-pass-system-uri-objects-instead-of-strings_1.cpp)]
[!code-csharp[FxCop.Usage.PassUri#1](../code-quality/codesnippet/CSharp/ca2234-pass-system-uri-objects-instead-of-strings_1.cs)]

## <a name="related-rules"></a>相关的规则

- [CA1057:字符串 URI 重载调用 System.Uri 重载](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)
- [CA1056:URI 属性不应为字符串](../code-quality/ca1056-uri-properties-should-not-be-strings.md)
- [CA1054:URI 参数不应为字符串](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)
- [CA1055:URI 返回值不应为字符串](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)