---
title: CA1822:将成员标记为 static
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- MarkMembersAsStatic
- CA1822
helpviewer_keywords:
- MarkMembersAsStatic
- CA1822
ms.assetid: 743f0af7-41d1-4852-8d97-af0688b31118
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 77b256ddaff769263bcc56891ca7c0ad2be30d0c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54979694"
---
# <a name="ca1822-mark-members-as-static"></a>CA1822:将成员标记为 static

|||
|-|-|
|TypeName|MarkMembersAsStatic|
|CheckId|CA1822|
|类别|Microsoft.Performance|
|是否重大更改|无间断-如果该成员不可见程序集外部的而不考虑更改进行。 否-如果只需将该成员更改为实例成员与`this`关键字。<br /><br /> 是-如果从实例成员的成员更改为静态成员，并且它是程序集外部可见。|

## <a name="cause"></a>原因
 不访问实例数据成员未标记为静态 (共享中[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)])。

## <a name="rule-description"></a>规则说明
 可以将不访问实例数据或不调用实例方法的成员标记为 static（在 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 中为 Shared）。 在将这些方法标记为 static 之后，编译器将向这些成员发出非虚拟调用站点。 发出非虚拟调用站点将禁止在运行时为每个调用，以确保当前的对象指针为非 null 检查。 这可以实现使性能敏感的代码得到显著提高。 在某些情况下，无法访问当前的对象实例表示存在正确性问题。

## <a name="how-to-fix-violations"></a>如何解决冲突
 将标记为静态成员 (或共享中[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) 或使用 this / Me 在方法正文，如果适用。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 它可以安全地禁止显示以前发布的代码的修复程序将为其在一项重大更改此规则的警告。

## <a name="related-rules"></a>相关的规则
 [CA1811:避免使用未调用的私有代码](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1812:避免未实例化的内部类](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1804:删除未使用的局部变量](../code-quality/ca1804-remove-unused-locals.md)