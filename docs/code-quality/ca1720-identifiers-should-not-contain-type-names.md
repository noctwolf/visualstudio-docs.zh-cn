---
title: CA1720:标识符不应包含类型名称
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1720
- IdentifiersShouldNotContainTypeNames
helpviewer_keywords:
- IdentifiersShouldNotContainTypeNames
- CA1720
ms.assetid: c95ee48f-f23a-45f0-ac9e-a3c1ecfabdea
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c596ddfa36beec696c275ea13b662ceebf8bde2c
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "65841797"
---
# <a name="ca1720-identifiers-should-not-contain-type-names"></a>CA1720:标识符不应包含类型名称

|||
|-|-|
|TypeName|IdentifiersShouldNotContainTypeNames|
|CheckId|CA1720|
|类别|Microsoft.Naming|
|是否重大更改|重大|

## <a name="cause"></a>原因

中成员的参数的名称包含的数据类型名称。

或

成员的名称包含特定于语言的数据类型名称。

默认情况下，此规则只看起来在外部可见成员，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

参数和成员的名称更好地用于进行通信来说明它们应由开发工具提供的类型及其含义。 有关成员的名称，如果必须使用数据类型名称，则使用而不是特定于语言的一个独立于语言的名称。 而不是，如C#类型名称`int`，使用独立于语言的数据类型名称， `Int32`。

每个离散的标记参数或成员的名称根据以下特定于语言的数据类型名称不区分大小写的方式检查：

- Bool
- WChar
- Int8
- UInt8
- Short
- UShort
- Int
- UInt
- 整数
- UInteger
- Long
- ULong
- 无符号
- 有符号
- Float
- Float32
- Float64

此外，参数的名称是还会检查以下独立于语言的数据类型名称不区分大小写的方式：

- 对象
- Obj
- Boolean
- Char
- String
- SByte
- Byte
- UByte
- Int16
- UInt16
- Int32
- UInt32
- Int64
- UInt64
- IntPtr
- ptr
- 指针
- UInptr
- UPtr
- UPointer
- Single
- Double
- 十进制
- GUID

## <a name="how-to-fix-violations"></a>如何解决冲突

**如果针对参数引发的：**

在参数名的数据类型标识符替换为更好地描述其含义的术语或更通用的词条，如 value。

**如果触发针对成员：**

替换为与更好地描述其含义，独立于语言的同等或更通用的词条，如 value 成员的名称的特定于语言的数据类型标识符。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

可能需要偶尔使用的基于类型的参数和成员名称。 但是，对于新的开发，没有已知情况下，则应该禁止显示此规则的警告。 对于以前发布的库，您可能需要禁止显示此规则的警告。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```ini
dotnet_code_quality.ca1720.api_surface = private, internal
```

此类别 （命名） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。

## <a name="related-rules"></a>相关的规则

- [CA1709:标识符应采用正确的大小写](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708:标识符不应不同于用例的详细信息](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
- [CA1707:标识符不应包含下划线](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)
- [CA1719:参数名不应与成员名称](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)