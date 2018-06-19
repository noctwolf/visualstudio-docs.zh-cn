---
title: CA1034：嵌套类型不应是可见的
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
helpviewer_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
ms.assetid: e9789a2c-2540-42a1-8705-ae7104011194
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a413f446a0fcd5dabdd430bc43dc48a1882ab80e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31900691"
---
# <a name="ca1034-nested-types-should-not-be-visible"></a>CA1034：嵌套类型不应是可见的
|||
|-|-|
|TypeName|NestedTypesShouldNotBeVisible|
|CheckId|CA1034|
|类别|Microsoft.Design|
|是否重大更改|重大|

## <a name="cause"></a>原因
 外部可见类型包含外部可见的类型声明。 嵌套的枚举和受保护的类型将与该规则中免除。

## <a name="rule-description"></a>规则说明
 嵌套的类型是在另一种类型的范围内声明的类型。 嵌套的类型可用于封装包含类型的私有实现详细信息。 如果用于此用途，则嵌套类型不应是外部可见的。

 用于逻辑分组，或以避免名称冲突; 请不要使用外部可见的嵌套的类型请改用命名空间。

 嵌套的类型包括的成员可访问性，其中某些程序员来说不清楚地了解的概念。

 子类和高级自定义应用场景中的嵌套的类型中，可以使用受保护的类型。

## <a name="how-to-fix-violations"></a>如何解决冲突
 如果你确实想要是外部可见的嵌套的类型，更改类型的可访问性。 否则，请从其父级中删除的嵌套的类型。 如果嵌套的目的是对其进行分类的嵌套的类型，使用命名空间以改为创建层次结构。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不禁止显示此规则发出的警告。

## <a name="example"></a>示例
 下面的示例演示与该规则冲突的类型。

 [!code-cpp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CPP/ca1034-nested-types-should-not-be-visible_1.cpp)]
 [!code-csharp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CSharp/ca1034-nested-types-should-not-be-visible_1.cs)]
 [!code-vb[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/VisualBasic/ca1034-nested-types-should-not-be-visible_1.vb)]