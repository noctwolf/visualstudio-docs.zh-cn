---
title: CA1309:使用按顺序的 StringComparison
ms.date: 11/04/2016
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
ms.openlocfilehash: 2c528266c54bbb2f3f0d9420461d700a46b09bd5
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922287"
---
# <a name="ca1309-use-ordinal-stringcomparison"></a>CA1309:使用按顺序的 StringComparison

|||
|-|-|
|TypeName|UseOrdinalStringComparison|
|CheckId|CA1309|
|类别|Microsoft.Globalization|
|是否重大更改|不间断|

## <a name="cause"></a>原因

Nonlinguistic 的字符串比较运算不会将<xref:System.StringComparison>参数设置为**Ordinal**或**stringcomparison.ordinalignorecase**。

## <a name="rule-description"></a>规则说明
许多字符串操作 (最重要的<xref:System.String.Compare%2A?displayProperty=fullName>是<xref:System.String.Equals%2A?displayProperty=fullName>和方法) 现在提供接受<xref:System.StringComparison?displayProperty=fullName>枚举值作为参数的重载。

指定**StringComparison**或**StringComparison**时, 字符串比较是非语义的。 也就是说, 在进行比较决策时, 将忽略特定于自然语言的功能。 忽略自然语言功能意味着决策基于简单的字节比较, 而不是按区域性参数化的大小写或相等表。 因此, 通过将参数显式设置为**StringComparison**或**StringComparison**, 你的代码通常会获得速度、提高正确性, 并变得更可靠。

## <a name="how-to-fix-violations"></a>如何解决冲突
若要修复与此规则的冲突, 请将字符串比较方法更改为接受<xref:System.StringComparison?displayProperty=fullName>枚举作为参数的重载, 并指定**序数**或**stringcomparison.ordinalignorecase**。 例如，将 `String.Compare(str1, str2)` 更改为 `String.Compare(str1, str2, StringComparison.Ordinal)`。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
如果库或应用程序适用于受限制的本地受众, 或应使用当前区域性的语义, 则可以安全地禁止显示此规则发出的警告。

## <a name="see-also"></a>请参阅

- [全球化警告](../code-quality/globalization-warnings.md)
- [CA1307指定 StringComparison](../code-quality/ca1307-specify-stringcomparison.md)