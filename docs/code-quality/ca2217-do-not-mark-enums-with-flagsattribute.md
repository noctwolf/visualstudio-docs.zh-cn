---
title: CA2217:不要使用 FlagsAttribute 标记枚举
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d8afe63de8630b3fa7466e8c0784c26ba00bb1ba
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53852474"
---
# <a name="ca2217-do-not-mark-enums-with-flagsattribute"></a>CA2217:不要使用 FlagsAttribute 标记枚举

|||
|-|-|
|TypeName|DoNotMarkEnumsWithFlags|
|CheckId|CA2217|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因

外部可见的枚举将标有<xref:System.FlagsAttribute>，和它与一个或多个值的两个或其他组合定义枚举值。

## <a name="rule-description"></a>规则说明

枚举应具有<xref:System.FlagsAttribute>存在仅当枚举中定义的每个值为两个或一系列的强大功能定义的值。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要修复此规则的冲突，请删除<xref:System.FlagsAttribute>枚举中。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不禁止显示此规则发出的警告。

## <a name="example-that-should-not-have-the-attribute"></a>不应具有的属性的示例

下面的示例演示一个枚举， `Color`，包含值 3。 3 不是两个或任何定义的值的组合的强大功能。 `Color`枚举不应标记有<xref:System.FlagsAttribute>。

[!code-cpp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_1.cpp)]
[!code-csharp[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_1.cs)]
[!code-vb[FxCop.Usage.EnumNoFlags#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_1.vb)]

## <a name="example-that-should-have-the-attribute"></a>应具有的属性的示例

下面的示例演示一个枚举`Days`，满足为标有需求的<xref:System.FlagsAttribute>。

[!code-cpp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CPP/ca2217-do-not-mark-enums-with-flagsattribute_2.cpp)]
[!code-csharp[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/CSharp/ca2217-do-not-mark-enums-with-flagsattribute_2.cs)]
[!code-vb[FxCop.Usage.EnumNoFlags2#1](../code-quality/codesnippet/VisualBasic/ca2217-do-not-mark-enums-with-flagsattribute_2.vb)]

## <a name="related-rules"></a>相关的规则

[CA1027:用 FlagsAttribute 标记枚举](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>请参阅

- <xref:System.FlagsAttribute?displayProperty=fullName>
