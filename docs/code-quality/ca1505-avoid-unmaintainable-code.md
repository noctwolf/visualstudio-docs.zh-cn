---
title: CA1505：避免编写无法维护的代码
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- AvoidUnmaintainableCode
- CA1505
helpviewer_keywords:
- AvoidUnmaintainableCode
- CA1505
ms.assetid: 8292b268-5929-4221-b699-f9c414bcec5d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b65e6c8c7826887e411b2210b613633c1e963aaf
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505：避免编写无法维护的代码
|||
|-|-|
|TypeName|AvoidUnmantainableCode|
|CheckId|CA1505|
|类别|Microsoft.Maintainability|
|是否重大更改|非重大|

## <a name="cause"></a>原因
 类型或方法具有较低的可维护性索引值。

## <a name="rule-description"></a>规则说明
 通过使用以下度量值来计算的可维护性索引： 代码、 程序卷和圈复杂度的行。 程序卷是了解类型或方法的运算符和操作数在代码中的数量为基础的难易程度的度量值。 圈复杂度是复杂性的一种结构化的类型或方法。 你可以了解有关在代码度量[测量复杂性和托管代码可维护性](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)。

 低的可维护性索引指示类型或方法可能难以维护，并且会重新设计的良好候选。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此冲突，重新设计的类型或方法，并尝试将它拆分为较小且更集中的类型或方法。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果类型或方法仍被视为可维护，尽管其尺寸大或者无法拆分的类型或方法中排除此警告。

## <a name="see-also"></a>请参阅
 [可维护性警告](../code-quality/maintainability-warnings.md)[测量复杂性和可维护性托管代码](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)