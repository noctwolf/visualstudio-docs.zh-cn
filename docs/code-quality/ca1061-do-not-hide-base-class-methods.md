---
title: CA1061:不要隐藏基类方法
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1061
- DoNotHideBaseClassMethods
helpviewer_keywords:
- DoNotHideBaseClassMethods
- CA1061
ms.assetid: 0bda9dc8-87b4-4038-ab9d-563298387466
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e0a6db369cea0e242ce5b2b6e169278b1bf17ea2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53928550"
---
# <a name="ca1061-do-not-hide-base-class-methods"></a>CA1061:不要隐藏基类方法

|||
|-|-|
|TypeName|DoNotHideBaseClassMethods|
|CheckId|CA1061|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 派生的类型声明的方法具有相同名称和具有相同数量的参数作为某一基方法;一个或多个参数是基方法; 中的相应参数的基类型和任何剩余的参数具有相同基方法中的相应参数的类型。

## <a name="rule-description"></a>规则说明
 只是在将较弱派生的基方法的参数签名中的对应类型相比的类型不同的派生方法的参数签名时，将由派生类型中具有相同名称方法隐藏基类型中的方法。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请删除或重命名方法，或更改的参数签名，以便该方法不会隐藏基方法。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例显示了与该规则冲突的方法。

 [!code-csharp[FxCop.Design.HideBaseMethod#1](../code-quality/codesnippet/CSharp/ca1061-do-not-hide-base-class-methods_1.cs)]