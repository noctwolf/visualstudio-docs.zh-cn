---
title: CA2136：成员不应有相互冲突的透明度注释
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2127
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2136
helpviewer_keywords:
- SecurityTransparentAssembliesShouldNotContainSecurityCriticalCode
- CA2127
ms.assetid: ff5a1d18-7c52-4da5-8990-60be83a8ea81
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: afcfe25a9ff4541331ddfc35ebe86bbf884ef02e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca2136-members-should-not-have-conflicting-transparency-annotations"></a>CA2136：成员不应有相互冲突的透明度注释
|||
|-|-|
|TypeName|TransparencyAnnotationsShouldNotConflict|
|CheckId|CA2136|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 当用标记类型成员时，将引发此规则<xref:System.Security>具有的成员的容器的安全属性不同的透明度的安全特性。

## <a name="rule-description"></a>规则说明
 将透明特性从较大作用域的代码元素应用到较小作用域的元素。 具有较大作用域的代码元素的透明特性优于第一个元素中包含的代码元素的透明特性。 例如，使用标记的类<xref:System.Security.SecurityCriticalAttribute>属性不能包含方法将标有<xref:System.Security.SecuritySafeCriticalAttribute>属性。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要解决此冲突，从具有较低范围的代码元素中删除安全特性，或更改其要包含的代码元素相同的属性。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不要禁止显示此规则的警告。

## <a name="example"></a>示例
 在下面的示例中的方法标记为<xref:System.Security.SecuritySafeCriticalAttribute>特性并且该类是与标记的类的成员<xref:System.Security.SecurityCriticalAttribute>属性。 应删除安全安全属性。

 [!code-csharp[FxCop.Security.CA2136.TransparencyAnnotationsShouldNotConflict#1](../code-quality/codesnippet/CSharp/ca2136-members-should-not-have-conflicting-transparency-annotations_1.cs)]