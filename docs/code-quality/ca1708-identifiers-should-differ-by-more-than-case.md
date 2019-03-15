---
title: CA1708:标识符应以大小写之外的差别进行区分
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 32ac2e430abdc068070457dcf362e39dcbc0b398
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57867539"
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708:标识符应以大小写之外的差别进行区分

|||
|-|-|
|TypeName|IdentifiersShouldDifferByMoreThanCase|
|CheckId|CA1708|
|类别|Microsoft.Naming|
|是否重大更改|重大|

## <a name="cause"></a>原因

两种类型、 成员、 参数或完全限定的命名空间的名称是相同的时它们会被转换为小写。

默认情况下，此规则仅查看外部可见的类型、 成员和命名空间，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

不能仅通过大小写区分命名空间、类型、成员和参数的标识符，因为针对公共语言运行时的语言不需要区分大小写。 例如，[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]是一种广泛使用的不区分大小写语言。

公开可见的成员将引发此规则。

## <a name="how-to-fix-violations"></a>如何解决冲突

选择时就与其他标识符的比较不区分大小写的方式是唯一的名称。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不禁止显示此规则发出的警告。 库可能不是在.NET Framework 中的所有可用语言中可用。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```
dotnet_code_quality.ca1708.api_surface = private, internal
```

此类别 （命名） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。

## <a name="example-of-a-violation"></a>冲突的示例

下面的示例演示了此规则的冲突。

[!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../code-quality/codesnippet/CSharp/ca1708-identifiers-should-differ-by-more-than-case_1.cs)]

## <a name="related-rules"></a>相关的规则

- [CA1709:标识符应采用正确的大小写](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)