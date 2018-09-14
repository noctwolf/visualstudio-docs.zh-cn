---
title: CA2219：在异常子句中不引发异常
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
helpviewer_keywords:
- DoNotRaiseExceptionsInExceptionClauses
- CA2219
ms.assetid: 7b9b0bee-4e8e-49a4-8c40-52142b49061f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e80409a1837da3e82e375561341f4fb4c3da9c28
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45548239"
---
# <a name="ca2219-do-not-raise-exceptions-in-exception-clauses"></a>CA2219：在异常子句中不引发异常
|||
|-|-|
|TypeName|DoNotRaiseExceptionsInExceptionClauses|
|CheckId|CA2219|
|类别|Microsoft.Usage|
|是否重大更改|非换行中断|

## <a name="cause"></a>原因
 从引发异常`finally`，筛选器或 fault 子句。

## <a name="rule-description"></a>规则说明
 当在异常子句中引发异常时，则会大大增加调试难度。

 在引发异常时`finally`或 fault 子句，新异常会隐藏活动异常，如果存在。 这使得原来的错误难以检测和调试。

 当筛选器子句中引发异常时，运行时以无提示方式捕获异常，并会导致筛选器来计算结果为 false。 没有办法指示计算为 false，并且从筛选器引发的异常的筛选器之间的差异。 这使得难以检测和调试的筛选器逻辑中的错误。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此冲突的此规则，则不要显式引发异常`finally`，筛选器或 fault 子句。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不要禁止显示此规则的警告。 没有在其下在异常子句中引发的异常提供了一项权益对执行代码的方案。

## <a name="related-rules"></a>相关的规则
 [CA1065：不要在意外的位置引发异常](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)

## <a name="see-also"></a>请参阅
 [设计警告](../code-quality/design-warnings.md)