---
title: CA1025:用形参数组替换重复的实参
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1025
- ReplaceRepetitiveArgumentsWithParamsArray
helpviewer_keywords:
- ReplaceRepetitiveArgumentsWithParamsArray
- CA1025
ms.assetid: f009b340-dea3-4459-8fe1-2143aa8b5d0b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4e4d2bb3330883e44b015698b740cd6403f953dc
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53868860"
---
# <a name="ca1025-replace-repetitive-arguments-with-params-array"></a>CA1025:用形参数组替换重复的实参

|||
|-|-|
|TypeName|ReplaceRepetitiveArgumentsWithParamsArray|
|CheckId|CA1025|
|类别|Microsoft.Design|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 公共类型中的公共或受保护方法具有三个以上参数，且其最后三个参数具有相同的类型。

## <a name="rule-description"></a>规则说明
 是未知的自变量的精确数目和变量自变量具有相同的类型，或可传递的类型相同时，请使用参数数组代替重复自变量。 例如，<xref:System.Console.WriteLine%2A>方法提供的常规用途的重载，用于接受任意数量的参数数组<xref:System.Object>参数。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此规则的冲突，请将重复的自变量替换为参数数组。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它始终是安全禁止显示此规则; 的警告但是，这种设计可能会导致可用性问题。

## <a name="example"></a>示例
 下面的示例显示了与此规则冲突的类型。

 [!code-csharp[FxCop.Design.RepeatArgs#1](../code-quality/codesnippet/CSharp/ca1025-replace-repetitive-arguments-with-params-array_1.cs)]