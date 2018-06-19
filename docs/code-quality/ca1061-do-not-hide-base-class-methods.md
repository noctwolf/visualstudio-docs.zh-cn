---
title: CA1061：不要隐藏基类方法
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
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
ms.openlocfilehash: dd0927a9b8bcd0f4be7c020a25a32d6c9675ca05
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31900533"
---
# <a name="ca1061-do-not-hide-base-class-methods"></a>CA1061：不要隐藏基类方法
|||
|-|-|
|TypeName|DoNotHideBaseClassMethods|
|CheckId|CA1061|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 派生的类型声明具有相同的名称并具有相同数量的参数作为其基方法; 这些方法之一方法一个或多个参数是基方法; 中的相应参数的基类型并且任何剩余的参数具有相同基方法中的相应参数的类型。

## <a name="rule-description"></a>规则说明
 如果派生方法的参数签名只是派生方式更弱的对应类型相比的参数签名中的基方法的类型方面有所不同，将由派生类型中的同名方法隐藏基类型中的方法。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，删除或重命名方法，或更改的参数签名，以便该方法不会隐藏基方法。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例演示与该规则冲突的方法。

 [!code-csharp[FxCop.Design.HideBaseMethod#1](../code-quality/codesnippet/CSharp/ca1061-do-not-hide-base-class-methods_1.cs)]