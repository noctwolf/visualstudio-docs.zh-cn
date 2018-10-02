---
title: CA2217： 不要标记枚举使用 FlagsAttribute |Microsoft Docs
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
- DoNotMarkEnumsWithFlags
- CA2217
helpviewer_keywords:
- DoNotMarkEnumsWithFlags
- CA2217
ms.assetid: 1b6f626c-66bf-45b0-a3e2-7c41ee9ceda7
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5d144d6f25e6ad7c867b1faed81e415466cc81e4
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "47587528"
---
# <a name="ca2217-do-not-mark-enums-with-flagsattribute"></a>CA2217：不要使用 FlagsAttribute 标记枚举
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA2217： 不要标记枚举使用 FlagsAttribute](https://docs.microsoft.com/visualstudio/code-quality/ca2217-do-not-mark-enums-with-flagsattribute)。

|||
|-|-|
|TypeName|DoNotMarkEnumsWithFlags|
|CheckId|CA2217|
|类别|Microsoft.Usage|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 外部可见的枚举将标有<xref:System.FlagsAttribute>和它与一个或多个值的两个或其他组合定义枚举值。

## <a name="rule-description"></a>规则说明
 枚举应具有<xref:System.FlagsAttribute>提供仅当枚举中定义的每个值的幂，或定义值的组合。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请删除<xref:System.FlagsAttribute>枚举中。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例显示了一个枚举，颜色，包含值 3，既不 2 的幂，也不定义的值的任意组合。 不应该用标记颜色枚举<xref:System.FlagsAttribute>。

 [!code-cpp[FxCop.Usage.EnumNoFlags#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.EnumNoFlags/cpp/FxCop.Usage.EnumNoFlags.cpp#1)]
 [!code-csharp[FxCop.Usage.EnumNoFlags#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.EnumNoFlags/cs/FxCop.Usage.EnumNoFlags.cs#1)]
 [!code-vb[FxCop.Usage.EnumNoFlags#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.EnumNoFlags/vb/FxCop.Usage.EnumNoFlags.vb#1)]

## <a name="example"></a>示例
 下面的示例演示一个枚举，天，满足标记为 System.FlagsAttribute 的要求。

 [!code-cpp[FxCop.Usage.EnumNoFlags2#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Usage.EnumNoFlags2/cpp/FxCop.Usage.EnumNoFlags2.cpp#1)]
 [!code-csharp[FxCop.Usage.EnumNoFlags2#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.EnumNoFlags2/cs/FxCop.Usage.EnumNoFlags2.cs#1)]
 [!code-vb[FxCop.Usage.EnumNoFlags2#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.EnumNoFlags2/vb/FxCop.Usage.EnumNoFlags2.vb#1)]

## <a name="related-rules"></a>相关的规则
 [CA1027：用 FlagsAttribute 标记枚举](../code-quality/ca1027-mark-enums-with-flagsattribute.md)

## <a name="see-also"></a>请参阅
 <xref:System.FlagsAttribute?displayProperty=fullName>



