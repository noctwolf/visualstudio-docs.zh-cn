---
title: CA2217:不要使用 FlagsAttribute 标记枚举
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- DoNotMarkEnumsWithFlags
- CA2217
helpviewer_keywords:
- DoNotMarkEnumsWithFlags
- CA2217
dev_langs:
- VB
- CSharp
- CPP
ms.assetid: 1b6f626c-66bf-45b0-a3e2-7c41ee9ceda7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: abe9b53a02f5a2c12b734c793557c69868a973e8
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841506"
---
# <a name="ca2217-do-not-mark-enums-with-flagsattribute"></a>CA2217:不要使用 FlagsAttribute 标记枚举

|||
|-|-|
|TypeName|DoNotMarkEnumsWithFlags|
|CheckId|CA2217|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因

枚举标记有<xref:System.FlagsAttribute>和它与一个或多个值的两个或其他组合定义枚举值。

默认情况下，此规则仅查看外部可见的枚举，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

枚举应具有<xref:System.FlagsAttribute>存在仅当枚举中定义的每个值为两个或一系列的强大功能定义的值。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复此规则的冲突，请删除<xref:System.FlagsAttribute>枚举中。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不禁止显示此规则发出的警告。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```ini
dotnet_code_quality.ca2217.api_surface = private, internal
```

此类别 （用法） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。

## <a name="examples"></a>示例

下面的代码演示一个枚举， `Color`，包含值 3。 3 不是两个或任何定义的值的组合的强大功能。 `Color`枚举不应标记有<xref:System.FlagsAttribute>。

[!code-cpp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_1.cpp)]
[!code-csharp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_1.cs)]
[!code-vb[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_1.vb)]

下面的代码演示一个枚举`Days`，满足为标有需求的<xref:System.FlagsAttribute>:

[!code-cpp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_2.cpp)]
[!code-csharp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_2.cs)]
[!code-vb[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_2.vb)]

## <a name="related-rules"></a>相关的规则

[CA1027:用 FlagsAttribute 标记枚举](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>请参阅

- <xref:System.FlagsAttribute?displayProperty=fullName>
