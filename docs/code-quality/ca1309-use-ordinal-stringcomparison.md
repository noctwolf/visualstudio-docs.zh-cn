---
title: CA1309:使用按顺序的 StringComparison
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- UseOrdinalStringComparison
- CA1309
helpviewer_keywords:
- UseOrdinalStringComparison
- CA1309
ms.assetid: 19be0854-cb6e-4efd-a4c8-a5c1fc6f7a71
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 677ade8a179974b2984827e9752b9783489187a0
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55043266"
---
# <a name="ca1309-use-ordinal-stringcomparison"></a>CA1309:使用按顺序的 StringComparison

|||
|-|-|
|TypeName|UseOrdinalStringComparison|
|CheckId|CA1309|
|类别|Microsoft.Globalization|
|是否重大更改|非换行|

## <a name="cause"></a>原因

非语义字符串比较操作不会设置<xref:System.StringComparison>为参数**序号**或**OrdinalIgnoreCase**。

## <a name="rule-description"></a>规则说明
 许多字符串运算，最重要的<xref:System.String.Compare%2A?displayProperty=fullName>并<xref:System.String.Equals%2A?displayProperty=fullName>方法，现在提供一个重载接受<xref:System.StringComparison?displayProperty=fullName>枚举作为参数的值。

 当您指定**StringComparison.Ordinal**或**StringComparison.OrdinalIgnoreCase**，字符串比较是非语义。 也就是说，进行比较的决策时，将忽略特定于自然语言的功能。 忽略自然语言功能意味着决策基于简单的字节比较而不在大小写或按区域性参数化的等效性表上。 因此，通过将参数显式设置为**StringComparison.Ordinal**或**StringComparison.OrdinalIgnoreCase**，你的代码通常获得速度、 提高正确性，并变得更可靠。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，请将字符串比较方法更改为重载接受<xref:System.StringComparison?displayProperty=fullName>枚举作为参数，并指定**序号**或**OrdinalIgnoreCase**。 例如，将 `String.Compare(str1, str2)` 更改为 `String.Compare(str1, str2, StringComparison.Ordinal)`。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它可以安全地禁止显示此规则的警告，当库或应用程序适用于有限的本地用户，或应使用当前区域性的语义。

## <a name="see-also"></a>请参阅

- [全球化警告](../code-quality/globalization-warnings.md)
- [CA1307:指定 StringComparison](../code-quality/ca1307-specify-stringcomparison.md)