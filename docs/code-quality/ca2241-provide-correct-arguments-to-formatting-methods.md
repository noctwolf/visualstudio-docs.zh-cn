---
title: CA2241:为格式化方法提供正确的参数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2241
- Provide correct arguments to formatting methods
- ProvideCorrectArgumentsToFormattingMethods
helpviewer_keywords:
- ProvideCorrectArgumentsToFormattingMethods
- CA2241
ms.assetid: 83639bc4-4c91-4a07-a40e-dc5e49a84494
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: f9f48f9cba146251aee1a58ffc7a3403ed899c4a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541462"
---
# <a name="ca2241-provide-correct-arguments-to-formatting-methods"></a>CA2241:为格式化方法提供正确的参数

|||
|-|-|
|TypeName|ProvideCorrectArgumentsToFormattingMethods|
|CheckId|CA2241|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 `format`字符串参数传递给方法，如<xref:System.Console.WriteLine%2A>， <xref:System.Console.Write%2A>，或<xref:System.String.Format%2A?displayProperty=fullName>不包含对应到每个对象自变量，或执行相反的格式项。

## <a name="rule-description"></a>规则说明
 等方法的参数<xref:System.Console.WriteLine%2A>， <xref:System.Console.Write%2A>，并<xref:System.String.Format%2A>包含多个后跟一个格式字符串<xref:System.Object?displayProperty=fullName>实例。 格式字符串包含文本和嵌入的格式项的窗体中，{索引 [，对齐方式] [: formatString]}。 “index”是一个从零开始的整数，用于指示要格式化的对象。 如果对象在格式字符串中没有对应的索引，则忽略该对象。 如果指定 index 的对象不存在，<xref:System.FormatException?displayProperty=fullName>在运行时引发。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请为每个对象自变量提供的格式项并提供每个格式项的对象参数。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例演示两个规则的冲突。

 [!code-vb[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/VisualBasic/ca2241-provide-correct-arguments-to-formatting-methods_1.vb)]
 [!code-csharp[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/CSharp/ca2241-provide-correct-arguments-to-formatting-methods_1.cs)]