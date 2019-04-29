---
title: CA1819:属性不应返回数组
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
helpviewer_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
ms.assetid: 85fcf312-57f8-438a-8b10-34441fe0bdeb
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 11209ec181e2c2b61c7767787ee99c2d69eabe8b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62545558"
---
# <a name="ca1819-properties-should-not-return-arrays"></a>CA1819:属性不应返回数组

|||
|-|-|
|TypeName|PropertiesShouldNotReturnArrays|
|CheckId|CA1819|
|类别|Microsoft.Performance|
|是否重大更改|重大|

## <a name="cause"></a>原因

属性返回一个数组。

默认情况下，此规则仅查看外部可见的属性和类型，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

数组返回的属性不受写保护，即使该属性是只读的。 若要使数组不会被更改，属性必须返回数组的副本。 通常情况下，用户不了解的不利性能影响的调用这样的属性。 具体而言，它们可能会使用属性作为索引的属性。

## <a name="how-to-fix-violations"></a>如何解决冲突

若要解决此规则的冲突，使方法的属性或更改要返回集合的属性。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

您可以禁止显示警告的属性的属性，其派生自引发<xref:System.Attribute>类。 属性可以包含返回数组的属性，但不能包含返回集合的属性。

如果该属性的一部分，可以禁止显示警告[数据传输对象 (DTO)](/previous-versions/msp-n-p/ff649585(v=pandp.10))类。

否则，不要禁止显示此规则的警告。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```
dotnet_code_quality.ca1819.api_surface = private, internal
```

此类别 （性能） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。

## <a name="example-violation"></a>冲突的示例

下面的示例显示了与此规则冲突的属性：

[!code-csharp[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_1.cs)]
[!code-vb[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_1.vb)]

若要解决此规则的冲突，使方法的属性或更改要返回的集合而不是数组的属性。

### <a name="change-the-property-to-a-method"></a>将属性更改为一种方法

下面的示例通过将属性更改为一种方法修复了冲突：

[!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_2.vb)]
[!code-csharp[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_2.cs)]

### <a name="change-the-property-to-return-a-collection"></a>更改属性，以返回集合

下面的示例通过将属性更改为返回修复了冲突<xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>:

[!code-csharp[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_3.cs)]
[!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_3.vb)]

## <a name="allow-users-to-modify-a-property"></a>允许用户修改属性

您可能想要允许使用者类的修改属性。 下面的示例显示了与此规则冲突的读/写属性：

[!code-csharp[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_4.cs)]
[!code-vb[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_4.vb)]

下面的示例通过将属性更改为返回修复了冲突<xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>:

[!code-vb[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_5.vb)]
[!code-csharp[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_5.cs)]

## <a name="related-rules"></a>相关的规则

- [CA1024： 在适用处在适用处使用属性](../code-quality/ca1024-use-properties-where-appropriate.md)