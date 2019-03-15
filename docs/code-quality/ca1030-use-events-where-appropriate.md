---
title: CA1030:在适用处使用事件
ms.date: 03/11/2019
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1054fa7b884c23edb76248cba17bab41cc64246f
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57867427"
---
# <a name="ca1030-use-events-where-appropriate"></a>CA1030:在适用处使用事件

|||
|-|-|
|TypeName|UseEventsWhereAppropriate|
|CheckId|CA1030|
|类别|Microsoft.Design|
|是否重大更改|非换行|

## <a name="cause"></a>原因

方法名称开头以下项之一：

- AddOn
- RemoveOn
- 激发
- 引发

默认情况下，此规则仅查看外部可见方法，但这是[可配置](#configurability)。

## <a name="rule-description"></a>规则说明

该规则检测名称通常用于事件的方法。 事件遵循观察者或发布-订阅设计模式;一个对象的状态更改必须传递给其他对象时使用它们。 如果调用的方法获取响应明确定义的状态更改，应通过事件处理程序调用该方法。 调用该方法的对象应引发事件而不是直接调用该方法。

在用户界面应用程序的用户操作，例如单击按钮会导致要执行的代码段中找到事件的一些常见示例。 .NET Framework 事件模型并不局限于用户界面;它应使用任何位置您必须进行通信的状态更改为一个或多个对象。

## <a name="how-to-fix-violations"></a>如何解决冲突

如果对象的状态发生更改时调用该方法，则应考虑更改设计为使用.NET 事件模式。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

如果该方法并不适用于.NET 事件模型，禁止显示此规则的警告。

## <a name="configurability"></a>可配置性

如果您运行此规则与[FxCop 分析器](install-fxcop-analyzers.md)（而不是通过静态代码分析），你可以配置的哪些部分在基本代码，以运行此规则，基于其可访问性。 例如，若要指定该规则应运行仅对非公共 API 外围应用，请到您的项目中的.editorconfig 文件添加以下键-值对：

```
dotnet_code_quality.ca1030.api_surface = private, internal
```

此类别 （设计） 中，可以配置此选项只是此规则，所有规则，或所有规则。 有关详细信息，请参阅[配置 FxCop 分析器](configure-fxcop-analyzers.md)。