---
title: CA1715:标识符应具有正确的前缀
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1715
- IdentifiersShouldHaveCorrectPrefix
helpviewer_keywords:
- IdentifiersShouldHaveCorrectPrefix
- CA1715
ms.assetid: cf45f8df-6855-4cb6-a4e2-7cfed714cf2f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: b794eb7c7a258a843763b2c68902000031c17eb3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62807142"
---
# <a name="ca1715-identifiers-should-have-correct-prefix"></a>CA1715:标识符应具有正确的前缀

|||
|-|-|
|TypeName|IdentifiersShouldHaveCorrectPrefix|
|CheckId|CA1715|
|类别|Microsoft.Naming|
|是否重大更改|是-如果在接口上引发。<br /><br /> 无间断-引发泛型类型参数上时。|

## <a name="cause"></a>原因

接口的名称不以大写 I 开头。

或

名称[泛型类型参数](/dotnet/csharp/programming-guide/generics/generic-type-parameters)类型或方法上不会启动包含大写 ' T '。

默认情况下，此规则仅查看外部可见的接口、 类型和方法，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

某些编程元素的名称按照约定，由特定前缀开头。

接口名称应以大写字母 I 后跟另一个大写字母开头。 此规则报告接口名称，例如 MyInterface 和 IsolatedInterface 的冲突。

泛型类型参数名称应以开头大写 ' T 和 （可选） 可以跟随另一个大写字母。 此规则报告泛型类型参数名称，例如 V 和 Type 的冲突。

命名约定提供了通用的外观对于库面向公共语言运行时。 这会减少所需的新软件库，并会增加客户信心库由必须在托管代码中开发的专业知识的人学习曲线。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置你的代码的哪些部分此规则分析。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。

### <a name="single-character-type-parameters"></a>单字符类型参数

你可以配置将单字符类型参数与该规则中排除。 例如，若要指定此规则*不应*分析单字符类型参数，将以下键 / 值对之一添加到你的项目中的.editorconfig 文件：

```
# Package version 2.9.0 and later
dotnet_code_quality.CA1715.exclude_single_letter_type_parameters = true

# Package version 2.6.3 and earlier
dotnet_code_quality.CA2007.allow_single_letter_type_parameters = true
```

> [!NOTE]
> 对于名为的类型参数将永远不会触发此规则`T`，例如， `Collection<T>`。

### <a name="api-surface"></a>API 图面

你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```
dotnet_code_quality.ca1715.api_surface = private, internal
```

此类别 （命名） 中，可以配置此选项只是此规则，所有规则，或所有规则。

## <a name="how-to-fix-violations"></a>如何解决冲突

重命名标识符，以便它正确的前缀。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

不禁止显示此规则发出的警告。

## <a name="interface-naming-example"></a>接口命名的示例

下面的代码段显示了不正确命名的接口：

[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_1.cpp)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_1.vb)]
[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_1.cs)]

下面的代码段通过接口前缀 i 来修复前面的冲突：

[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_2.cs)]
[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_2.cpp)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix2#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_2.vb)]

## <a name="type-parameter-naming-example"></a>类型参数的命名示例

下面的代码段显示了一个未正确命名的泛型类型参数：

[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_3.cpp)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_3.vb)]
[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix3#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_3.cs)]

下面的代码段通过前缀与 T 的泛型类型参数修复了上一冲突:

[!code-cpp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CPP/ca1715-identifiers-should-have-correct-prefix_4.cpp)]
[!code-csharp[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/CSharp/ca1715-identifiers-should-have-correct-prefix_4.cs)]
[!code-vb[FxCop.Naming.IdentifiersShouldHaveCorrectPrefix4#1](../code-quality/codesnippet/VisualBasic/ca1715-identifiers-should-have-correct-prefix_4.vb)]

## <a name="related-rules"></a>相关的规则

- [CA1722:标识符应采用正确的前缀](../code-quality/ca1722-identifiers-should-not-have-incorrect-prefix.md)