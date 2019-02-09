---
title: CA1821:移除空终结器
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- RemoveEmptyFinalizers
- CA1821
helpviewer_keywords:
- CA1821
ms.assetid: 3f4855a0-e4a0-46e6-923c-4c3b7074048d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 16bb2786c4c7b0ca94fe60a9577e4b462d663bfc
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55957843"
---
# <a name="ca1821-remove-empty-finalizers"></a>CA1821:移除空终结器

|||
|-|-|
|TypeName|RemoveEmptyFinalizers|
|CheckId|CA1821|
|类别|Microsoft.Performance|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 一个类型实现终结器为空、 调用仅基类型终结器，或只按条件发出的方法调用。

## <a name="rule-description"></a>规则说明
 应尽可能避免终结器，因为跟踪对象生存期会产生额外的性能系统开销。 它收集对象前，垃圾回收器将运行终结器。 这意味着两个集合需要回收该对象。 空终结器会产生此增加的开销毫无益处。

## <a name="how-to-fix-violations"></a>如何解决冲突
 移除空终结器。 如果终结器才可进行调试，则将在整个终结器`#if DEBUG / #endif`指令。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不要禁止显示此规则的消息。 取消终止失败会降低性能，并不提供任何好处。

## <a name="example"></a>示例
 下面的示例显示了应移除空终结器、 终结器应括起来的`#if DEBUG / #endif`指令和使用终结器`#if DEBUG / #endif`指令正确。

 [!code-csharp[FxCop.Performance.RemoveEmptyFinalizers#1](../code-quality/codesnippet/CSharp/ca1821-remove-empty-finalizers_1.cs)]