---
title: CA1800:避免进行不必要的强制转换
ms.date: 10/26/2017
ms.topic: reference
f1_keywords:
- CA1800
- DoNotCastUnnecessarily
helpviewer_keywords:
- DoNotCastUnnecessarily
- CA1800
ms.assetid: b79a010a-6627-421e-8955-6007e32fa808
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- VB
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: a13aeeffbc77e4f40ff886c0d890f181697fcc11
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55950677"
---
# <a name="ca1800-do-not-cast-unnecessarily"></a>CA1800:避免进行不必要的强制转换

|||
|-|-|
|TypeName|DoNotCastUnnecessarily|
|CheckId|CA1800|
|类别|Microsoft.Performance|
|是否重大更改|非换行|

## <a name="cause"></a>原因
一种方法对其参数或局部变量之一执行重复强制转换。

有关此规则的完整分析，必须使用调试信息生成测试的程序集和关联的程序数据库 (.pdb) 文件必须可用。

## <a name="rule-description"></a>规则说明
重复强制转换会降低性能，特别是在精简的迭代语句中执行强制转换时。 对于显式重复强制转换操作，将强制转换的结果存储在本地变量和使用本地变量，而不是重复强制转换操作。

如果 C#`is`运算符用于测试是否之前执行实际的强制转换，转换将成功完成测试的结果，请考虑`as`运算符相反。 这提供了相同的功能而无需执行的隐式强制转换操作`is`运算符。 或者，在 C# 7.0 及更高版本，使用`is`运算符，其中[模式匹配](/dotnet/csharp/language-reference/keywords/is#pattern-matching-with-is)检查类型转换，并将该类型的变量的表达式强制转换在一个步骤中。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请修改要强制转换操作的数量降至最低的方法实现。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果性能不是一个问题，它是安全地禁止显示此规则的警告，或者完全忽略此规则。

## <a name="examples"></a>示例
 下面的示例演示使用 C# 违反了此规则的方法`is`运算符。 第二种方法通过替换来满足该规则`is`运算符的结果对测试与`as`运算符，这将降低每次迭代两个到一个强制转换操作的数目。 第三种方法也满足该规则使用`is`与[模式匹配](/dotnet/csharp/language-reference/keywords/is#pattern-matching-with-is)以创建所需类型的变量，如果类型转换会成功。

 [!code-csharp[FxCop.Performance.UnnecessaryCastsAsIs#1](../code-quality/codesnippet/CSharp/ca1800-do-not-cast-unnecessarily_1.cs)]

 下面的示例演示一种方法， `start_Click`，具有多个重复的显式转换，这违反了规则和一种方法， `reset_Click`，以及通过在本地变量中存储转换满足该规则。

 [!code-vb[FxCop.Performance.UnnecessaryCasts#1](../code-quality/codesnippet/VisualBasic/ca1800-do-not-cast-unnecessarily_2.vb)]
 [!code-csharp[FxCop.Performance.UnnecessaryCasts#1](../code-quality/codesnippet/CSharp/ca1800-do-not-cast-unnecessarily_2.cs)]

## <a name="see-also"></a>请参阅

- [as （C# 参考）](/dotnet/csharp/language-reference/keywords/as)
- [is （C# 参考）](/dotnet/csharp/language-reference/keywords/is)