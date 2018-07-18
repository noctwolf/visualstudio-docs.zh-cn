---
title: CA1043：将整型或字符串自变量用于索引器
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
helpviewer_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ad1a25f33ce91fba7b2be8723b86067afe81632c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31900081"
---
# <a name="ca1043-use-integral-or-string-argument-for-indexers"></a>CA1043：将整型或字符串自变量用于索引器
|||
|-|-|
|TypeName|UseIntegralOrStringArgumentForIndexers|
|CheckId|CA1043|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 公共或受保护类型包含公共或受保护的索引器，而不使用索引类型<xref:System.Int32?displayProperty=fullName>， <xref:System.Int64?displayProperty=fullName>， <xref:System.Object?displayProperty=fullName>，或<xref:System.String?displayProperty=fullName>。

## <a name="rule-description"></a>规则说明
 索引器，即索引属性，应将整型或字符串类型用于索引。 这些类型通常用于数据结构编制索引，并且提高库的可用性。 利用<xref:System.Object>类型应被限制为这些情况下，其中在设计时无法指定特定整型或字符串类型。 如果设计需要其他类型的索引，请重新考虑是否类型表示的逻辑数据存储区。 如果它不表示逻辑数据存储，使用方法。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，将索引更改为整数或字符串类型，或使用一种方法，而不是索引器。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 禁止显示此规则仅在仔细考虑对非标准的索引器的需求后的警告。

## <a name="example"></a>示例
 下面的示例演示使用一个索引器<xref:System.Int32>索引。

 [!code-csharp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CSharp/ca1043-use-integral-or-string-argument-for-indexers_1.cs)]
 [!code-cpp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CPP/ca1043-use-integral-or-string-argument-for-indexers_1.cpp)]
 [!code-vb[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/VisualBasic/ca1043-use-integral-or-string-argument-for-indexers_1.vb)]

## <a name="related-rules"></a>相关的规则
 [CA1023：索引器不应是多维的](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)

 [CA1024：在适用处使用属性](../code-quality/ca1024-use-properties-where-appropriate.md)