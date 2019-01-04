---
title: CA1820:使用字符串长度测试是否有空字符串
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
helpviewer_keywords:
- TestForEmptyStringsUsingStringLength
- CA1820
ms.assetid: da1e70c8-b1dc-46b9-8b8f-4e6e48339681
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bc3d0e0f25d776a879cfc0ca761ee89fa35e056a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53900647"
---
# <a name="ca1820-test-for-empty-strings-using-string-length"></a>CA1820:使用字符串长度测试是否有空字符串

|||
|-|-|
|TypeName|TestForEmptyStringsUsingStringLength|
|CheckId|CA1820|
|类别|Microsoft.Performance|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 使用为空字符串比较字符串<xref:System.Object.Equals%2A?displayProperty=fullName>。

## <a name="rule-description"></a>规则说明
 比较字符串使用<xref:System.String.Length%2A?displayProperty=fullName>属性或<xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName>方法是明显快于使用<xref:System.Object.Equals%2A>。 这是因为<xref:System.Object.Equals%2A>执行以外的更多 MSIL 指令<xref:System.String.IsNullOrEmpty%2A>或执行要检索的指令数<xref:System.String.Length%2A>属性值和比较为零。

 应注意，<xref:System.Object.Equals%2A>和<xref:System.String.Length%2A>= = 0 的空字符串的行为有所不同。 如果尝试获取的值<xref:System.String.Length%2A>null 字符串的属性，公共语言运行时将引发<xref:System.NullReferenceException?displayProperty=fullName>。 如果执行 null 字符串和空字符串之间的比较，公共语言运行时不会引发异常;比较返回`false`。 测试 null 不显著影响这两种方法的相对性能。 面向时[!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]，使用<xref:System.String.IsNullOrEmpty%2A>方法。 否则，请使用<xref:System.String.Length%2A>= = 比较只要有可能。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请更改要使用的比较<xref:System.String.Length%2A>属性和 null 字符串的测试。 如果面向[!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]，使用<xref:System.String.IsNullOrEmpty%2A>方法。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它可以安全地禁止显示此规则的警告，如果性能不是问题。

## <a name="example"></a>示例
 下面的示例说明了用于查找空字符串的不同技术。

 [!code-csharp[FxCop.Performance.StringTest#1](../code-quality/codesnippet/CSharp/ca1820-test-for-empty-strings-using-string-length_1.cs)]