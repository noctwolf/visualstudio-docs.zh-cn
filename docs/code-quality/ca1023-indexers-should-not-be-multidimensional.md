---
title: CA1023:索引器不应是多维的
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IndexersShouldNotBeMultidimensional
- CA1023
helpviewer_keywords:
- CA1023
- IndexersShouldNotBeMultidimensional
ms.assetid: ae499879-97f6-434e-a61d-1fedd231d2fb
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: ef3afd9dda70d02698abec5459b36e6acc2c5ed0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62779611"
---
# <a name="ca1023-indexers-should-not-be-multidimensional"></a>CA1023:索引器不应是多维的

|||
|-|-|
|TypeName|IndexersShouldNotBeMultidimensional|
|CheckId|CA1023|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 公共或受保护类型包含公共或受保护的索引器使用多个索引。

## <a name="rule-description"></a>规则说明
 索引器，也就是说，索引属性，应使用单个索引。 多维索引器会显著降低库的可用性。 如果设计需要多个索引，请重新考虑是否该类型表示逻辑数据存储区。 否则，请使用一种方法。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请更改设计，以使用长整型或字符串索引或使用一种方法，而不是索引器。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 禁止显示此规则仅在仔细考虑要使用非标准索引器后的警告。

## <a name="example"></a>示例
 下面的示例演示一种类型， `DayOfWeek03`，使用与该规则冲突多维索引器。 索引器可将其视为一种转换，并因此更恰当地公开的方法。 类型重新设计了`RedesignedDayOfWeek03`以满足该规则。

 [!code-vb[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/VisualBasic/ca1023-indexers-should-not-be-multidimensional_1.vb)]
 [!code-cpp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CPP/ca1023-indexers-should-not-be-multidimensional_1.cpp)]
 [!code-csharp[FxCop.Design.OneDimensionForIndexer#1](../code-quality/codesnippet/CSharp/ca1023-indexers-should-not-be-multidimensional_1.cs)]

## <a name="related-rules"></a>相关的规则
 [CA1043:使用整型或字符串参数用于索引器](../code-quality/ca1043-use-integral-or-string-argument-for-indexers.md)

 [CA1024： 在适用处在适用处使用属性](../code-quality/ca1024-use-properties-where-appropriate.md)