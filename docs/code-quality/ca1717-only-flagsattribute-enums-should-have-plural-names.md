---
title: CA1717:只有 FlagsAttribute 枚举应采用复数形式的名称
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1717
- OnlyFlagsEnumsShouldHavePluralNames
helpviewer_keywords:
- OnlyFlagsEnumsShouldHavePluralNames
- CA1717
ms.assetid: a6855d8b-d78a-42c1-834e-61c31f5572ed
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f8fa009c93f049938a198eabd1a5dcc86a45caa7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54957242"
---
# <a name="ca1717-only-flagsattribute-enums-should-have-plural-names"></a>CA1717:只有 FlagsAttribute 枚举应采用复数形式的名称

|||
|-|-|
|TypeName|OnlyFlagsEnumsShouldHavePluralNames|
|CheckId|CA1717|
|类别|Microsoft.Naming|
|是否重大更改|重大|

## <a name="cause"></a>原因
 外部可见的枚举的名称以复数形式的单词结尾并且枚举未标有<xref:System.FlagsAttribute?displayProperty=fullName>属性。

## <a name="rule-description"></a>规则说明
 命名约定规定，复数形式的名称的一个枚举，指示可以同时指定多个枚举的值。 <xref:System.FlagsAttribute>告知编译器应将枚举视为位字段，它允许对枚举的按位运算。

 如果仅一次，可以指定一个枚举值，该枚举的名称应为单数形式的单词。 例如，枚举，用于定义每周天数可能被用于应用程序中您可以在其中指定多天。 此枚举应具有<xref:System.FlagsAttribute>且无法调用天。 允许仅指定一天的类似枚举将没有属性，并可能是名为 Day。

 命名约定提供了通用的外观对于库面向公共语言运行时。 这将减少所需了解新的软件库，并使客户进一步库由在托管代码开发具有专业知识的人员的时间。

## <a name="how-to-fix-violations"></a>如何解决冲突
 单数形式的单词进行枚举的名称或添加<xref:System.FlagsAttribute>。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它可以安全地禁止显示规则的警告，如果以单数形式的单词结尾的名称。

## <a name="related-rules"></a>相关的规则
 [CA1714:枚举应采用复数形式的名称](../code-quality/ca1714-flags-enums-should-have-plural-names.md)

 [CA1027:用 FlagsAttribute 标记枚举](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217:不使用 FlagsAttribute 标记枚举](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>请参阅

- <xref:System.FlagsAttribute?displayProperty=fullName>
- [枚举设计](/dotnet/standard/design-guidelines/enum)