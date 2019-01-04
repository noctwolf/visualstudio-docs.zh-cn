---
title: CA1030:在适用处使用事件
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- UseEventsWhereAppropriate
- CA1030
helpviewer_keywords:
- CA1030
- UseEventsWhereAppropriate
ms.assetid: ea051367-deeb-40f9-9b65-eb818f1e133a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 445330d654e870fe12aa2ca19626377972235eac
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53860801"
---
# <a name="ca1030-use-events-where-appropriate"></a>CA1030:在适用处使用事件

|||
|-|-|
|TypeName|UseEventsWhereAppropriate|
|CheckId|CA1030|
|类别|Microsoft.Design|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 公共、 受保护或私有方法名称以与以下项之一：

- 外接程序

- RemoveOn

- 激发

- 引发

## <a name="rule-description"></a>规则说明
 该规则检测名称通常用于事件的方法。 事件遵循观察者或发布-订阅设计模式;一个对象的状态更改必须传递给其他对象时使用它们。 如果调用的方法获取响应明确定义的状态更改，应通过事件处理程序调用该方法。 调用该方法的对象应引发事件而不是直接调用该方法。

 在用户界面应用程序的用户操作，例如单击按钮会导致要执行的代码段中找到事件的一些常见示例。 .NET Framework 事件模型并不局限于用户界面;它应使用任何位置您必须进行通信的状态更改为一个或多个对象。

## <a name="how-to-fix-violations"></a>如何解决冲突
 如果对象的状态发生更改时调用该方法，则应考虑更改设计为使用.NET Framework 事件模式。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果该方法并不适用于.NET Framework 事件模型，禁止显示此规则的警告。