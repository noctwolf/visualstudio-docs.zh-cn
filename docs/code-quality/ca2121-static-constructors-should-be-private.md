---
title: CA2121：静态构造函数应为私有
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
helpviewer_keywords:
- CA2121
- StaticConstructorsShouldBePrivate
ms.assetid: ee93c620-8fc1-4e47-866c-d389c3ca9f2e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4f6eef1097565090fd1b9be572f9a33afed9afed
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca2121-static-constructors-should-be-private"></a>CA2121：静态构造函数应为私有
|||
|-|-|
|TypeName|StaticConstructorsShouldBePrivate|
|CheckId|CA2121|
|类别|Microsoft.Security|
|是否重大更改|重大|

## <a name="cause"></a>原因
 一种类型具有不是私有静态构造函数。

## <a name="rule-description"></a>规则说明
 静态构造函数，也称为类构造函数，用于初始化类型。 系统在创建第一个类型实例或引用任何静态成员之前调用静态构造函数。 用户具有无法控制当调用该静态构造函数。 如果静态构造函数不是私有，则系统以外的代码可以调用它。 根据构造函数中执行的操作，这可能导致意外行为。

 此规则由 C# 和 Visual Basic 编译器强制执行。

## <a name="how-to-fix-violations"></a>如何解决冲突
 冲突通常是由以下操作之一导致的：

-   为你的类型定义静态构造函数和未将它设置为私有。

-   编程语言编译器添加到你的类型的默认静态构造函数和未将它设置为私有。

 若要解决的冲突的第一个类型，请将静态构造函数专用。 若要解决第二种，请与您的类型添加私有静态构造函数。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 不要禁止显示这些冲突。 如果你的软件设计需要显式调用静态构造函数，则很可能的设计包含严重缺陷和应评审。