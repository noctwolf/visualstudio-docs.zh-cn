---
title: CA1717:只有 FlagsAttribute 枚举应采用复数形式的名称
ms.date: 03/11/2019
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
ms.openlocfilehash: 2d760802422773b3713fa7ea08ce0ce7a191f418
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547111"
---
# <a name="ca1717-only-flagsattribute-enums-should-have-plural-names"></a>CA1717:只有 FlagsAttribute 枚举应采用复数形式的名称

|||
|-|-|
|TypeName|OnlyFlagsEnumsShouldHavePluralNames|
|CheckId|CA1717|
|类别|Microsoft.Naming|
|是否重大更改|重大|

## <a name="cause"></a>原因

枚举的名称以复数形式结束, 并且未使用<xref:System.FlagsAttribute?displayProperty=fullName>特性标记枚举。

默认情况下, 此规则仅查看外部可见的枚举, 但这是[可配置](#configurability)的。

## <a name="rule-description"></a>规则说明

命名约定规定, 复数名称的枚举指示可以同时指定多个枚举值。 <xref:System.FlagsAttribute>告诉编译器, 应将枚举视为对枚举启用按位运算的位域。

如果一次只能指定一个枚举值, 则枚举的名称应为单数形式的单词。 例如, 定义一周中各天的枚举可能适用于可指定多天的应用程序。 此枚举应具有<xref:System.FlagsAttribute> , 并且可以称为 "Days"。 只允许指定一天的类似枚举不具有属性, 并且可以称为 "Day"。

命名约定为面向公共语言运行时的库提供了通用的外观。 这减少了学习新软件库所需的时间, 并使客户对库的开发更加自信, 因为有开发托管代码的专业技能。

## <a name="how-to-fix-violations"></a>如何解决冲突

使枚举名称成为单数字或添加<xref:System.FlagsAttribute>。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

如果名称以单数形式出现, 则可以安全地禁止显示规则。

## <a name="configurability"></a>配置

如果从[FxCop 分析器](install-fxcop-analyzers.md)(而不是传统分析) 运行此规则, 则可以根据其可访问性, 将基本代码的哪些部分配置为在上运行此规则。 例如, 若要指定规则只应针对非公共 API 图面运行, 请在项目中的 editorconfig 文件中添加以下键/值对:

```ini
dotnet_code_quality.ca1717.api_surface = private, internal
```

您可以为此规则、所有规则或此类别中的所有规则 (命名) 配置此选项。 有关详细信息, 请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。

## <a name="related-rules"></a>相关规则

- [CA1714标志枚举应包含复数名称](../code-quality/ca1714-flags-enums-should-have-plural-names.md)
- [CA1027用 FlagsAttribute 标记枚举](../code-quality/ca1027-mark-enums-with-flagsattribute.md)
- [CA2217不要用 FlagsAttribute 标记枚举](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>请参阅

- <xref:System.FlagsAttribute?displayProperty=fullName>
- [枚举设计](/dotnet/standard/design-guidelines/enum)