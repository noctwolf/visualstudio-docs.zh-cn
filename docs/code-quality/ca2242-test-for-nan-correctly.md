---
title: CA2242:正确测试 NaN
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- TestForNaNCorrectly
- CA2242
helpviewer_keywords:
- CA2242
ms.assetid: e12dcffc-e255-4e1e-8fdf-3c6054d44abe
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 43c2dd1f6a23c3df4d77207efb49531b97b3b381
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55929045"
---
# <a name="ca2242-test-for-nan-correctly"></a>CA2242:正确测试 NaN

|||
|-|-|
|TypeName|TestForNaNCorrectly|
|CheckId|CA2242|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 一个表达式测试值与<xref:System.Single.NaN?displayProperty=fullName>或<xref:System.Double.NaN?displayProperty=fullName>。

## <a name="rule-description"></a>规则说明
 <xref:System.Double.NaN?displayProperty=fullName>这表示未一个数字，结果时未定义的算术运算。 任何表达式，以便测试在值之间的相等性和<xref:System.Double.NaN?displayProperty=fullName>始终返回`false`。 任何表达式，以便测试在值之间的不相等并<xref:System.Double.NaN?displayProperty=fullName>始终返回`true`。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，并准确地确定某个值是否表示<xref:System.Double.NaN?displayProperty=fullName>，使用<xref:System.Single.IsNaN%2A?displayProperty=fullName>或<xref:System.Double.IsNaN%2A?displayProperty=fullName>来测试值。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例演示两个错误地测试对值的表达式<xref:System.Double.NaN?displayProperty=fullName>和正确使用的表达式，<xref:System.Double.IsNaN%2A?displayProperty=fullName>来测试值。

 [!code-vb[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/VisualBasic/ca2242-test-for-nan-correctly_1.vb)]
 [!code-csharp[FxCop.Usage.TestForNaN#1](../code-quality/codesnippet/CSharp/ca2242-test-for-nan-correctly_1.cs)]