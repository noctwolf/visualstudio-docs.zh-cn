---
title: CA1712： 不要使用类型名称的枚举值的前缀 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1712
- DoNotPrefixEnumValuesWithTypeName
helpviewer_keywords:
- CA1712
- DoNotPrefixEnumValuesWithTypeName
ms.assetid: df0e3a12-67bf-48f1-a10b-2ef60484a5c7
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 9283c35dacc0d3f3779a167eeb095f90431d7a4c
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "47587675"
---
# <a name="ca1712-do-not-prefix-enum-values-with-type-name"></a>CA1712：不要将类型名用作枚举值的前缀
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA1712： 不要使用类型名称的枚举值的前缀](https://docs.microsoft.com/visualstudio/code-quality/ca1712-do-not-prefix-enum-values-with-type-name)。

|||
|-|-|
|TypeName|DoNotPrefixEnumValuesWithTypeName|
|CheckId|CA1712|
|类别|Microsoft.Naming|
|是否重大更改|重大|

## <a name="cause"></a>原因
 一个枚举，包含作为名称开头的枚举类型名称的成员。

## <a name="rule-description"></a>规则说明
 由于类型信息需要由开发工具提供的枚举成员的名称将不使用前缀的类型名称。

 命名约定提供了通用的外观对于库面向公共语言运行时。 这将减少需要，若要了解新的软件库，并且会增加客户信心库由在托管代码开发具有专业知识的人员的时间。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，请从该枚举成员中删除类型名称前缀。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例演示的修正版本后跟一个未正确命名的枚举。

 [!code-cpp[FxCop.Naming.EnumValues#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Naming.EnumValues/cpp/FxCop.Naming.EnumValues.cpp#1)]
 [!code-csharp[FxCop.Naming.EnumValues#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Naming.EnumValues/cs/FxCop.Naming.EnumValues.cs#1)]
 [!code-vb[FxCop.Naming.EnumValues#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Naming.EnumValues/vb/FxCop.Naming.EnumValues.vb#1)]

## <a name="related-rules"></a>相关的规则
 [CA1711：标识符应采用正确的后缀](../code-quality/ca1711-identifiers-should-not-have-incorrect-suffix.md)

 [CA1027：用 FlagsAttribute 标记枚举](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

 [CA2217：不要使用 FlagsAttribute 标记枚举](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>请参阅
 <xref:System.Enum?displayProperty=fullName>



