---
title: CA2241：为格式化方法提供正确的自变量
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5c695c9f6e8af0e61bed88fd5a880e5655ecb7d6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca2241-provide-correct-arguments-to-formatting-methods"></a>CA2241：为格式化方法提供正确的自变量
|||
|-|-|
|TypeName|ProvideCorrectArgumentsToFormattingMethods|
|CheckId|CA2241|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 `format`字符串自变量传递到方法，如<xref:System.Console.WriteLine%2A>， <xref:System.Console.Write%2A>，或<xref:System.String.Format%2A?displayProperty=fullName>不包含格式项对应到每个对象参数，反之亦然。

## <a name="rule-description"></a>规则说明
 方法的自变量<xref:System.Console.WriteLine%2A>， <xref:System.Console.Write%2A>，和<xref:System.String.Format%2A>包含一个格式字符串后, 接几个<xref:System.Object?displayProperty=fullName>实例。 格式字符串由文本和嵌入的格式项的窗体中，{索引 [，对齐] [: formatString]}。 “index”是一个从零开始的整数，用于指示要格式化的对象。 如果一个对象的格式字符串中没有相应的索引，则忽略该对象。 如果指定 index 的对象不存在，<xref:System.FormatException?displayProperty=fullName>在运行时引发。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，为每个对象自变量提供的格式项，并提供每个格式项的对象自变量。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例演示两个冲突的规则的情况。

 [!code-vb[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/VisualBasic/ca2241-provide-correct-arguments-to-formatting-methods_1.vb)]
 [!code-csharp[FxCop.Usage.FormattingArguments#1](../code-quality/codesnippet/CSharp/ca2241-provide-correct-arguments-to-formatting-methods_1.cs)]