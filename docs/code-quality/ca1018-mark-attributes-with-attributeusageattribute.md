---
title: CA1018:用 AttributeUsageAttribute 标记特性
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
helpviewer_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
ms.assetid: 6ab70ec0-220f-4880-af31-45067703133c
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: dfdaca64c166a29ad731719f79bbad57e975ff8b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "55043721"
---
# <a name="ca1018-mark-attributes-with-attributeusageattribute"></a>CA1018:用 AttributeUsageAttribute 标记特性

|||
|-|-|
|TypeName|MarkAttributesWithAttributeUsage|
|CheckId|CA1018|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 <xref:System.AttributeUsageAttribute?displayProperty=fullName>属性上不存在自定义属性。

## <a name="rule-description"></a>规则说明
 在定义的自定义属性时，将其标记使用<xref:System.AttributeUsageAttribute>以指示源代码中可以应用自定义特性的位置。 特性的含义和预定用法将决定它在代码中的有效位置。 例如，可以定义标识由谁来负责维护和增强在库中，每种类型和在类型级别始终分配职责的人员的属性。 在这种情况下，应启用的属性类、 枚举和接口，但不是应启用它的方法、 事件或属性上编译器。 组织的策略和过程将指示是否应在程序集上启用该属性。

 <xref:System.AttributeTargets?displayProperty=fullName>枚举定义可以为自定义属性指定的目标。 如果省略<xref:System.AttributeUsageAttribute>，定义的自定义属性才有效的所有目标`All`的值<xref:System.AttributeTargets>枚举。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，通过使用指定的属性的目标<xref:System.AttributeUsageAttribute>。 请参见以下示例。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 您应修复而不包括该消息的不是此规则的冲突。 即使属性继承<xref:System.AttributeUsageAttribute>，该属性应存在以简化代码维护。

## <a name="example"></a>示例
 下面的示例定义两个属性。 `BadCodeMaintainerAttribute` 错误地省略<xref:System.AttributeUsageAttribute>语句，和`GoodCodeMaintainerAttribute`正确地实现在本部分中前面所述的属性。 请注意，该属性`DeveloperName`所需的设计规则[CA1019:定义特性参数的访问器](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)，包含在出于完整性的考虑。

 [!code-csharp[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/CSharp/ca1018-mark-attributes-with-attributeusageattribute_1.cs)]
 [!code-vb[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/VisualBasic/ca1018-mark-attributes-with-attributeusageattribute_1.vb)]

## <a name="related-rules"></a>相关的规则
 [CA1019:定义特性参数的访问器](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)

 [CA1813:避免使用未密封的特性](../code-quality/ca1813-avoid-unsealed-attributes.md)

## <a name="see-also"></a>请参阅

- [属性](/dotnet/standard/design-guidelines/attributes)