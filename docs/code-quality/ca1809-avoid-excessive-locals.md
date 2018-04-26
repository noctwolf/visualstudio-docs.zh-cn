---
title: CA1809：避免过多的局部变量
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1809
- AvoidExcessiveLocals
helpviewer_keywords:
- AvoidExcessiveLocals
- CA1809
ms.assetid: 5c81ea43-cb49-448f-980f-a1dd9764043c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ea0d1d27f583e86a62e9c0ff524d9d623253d007
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="ca1809-avoid-excessive-locals"></a>CA1809：避免过多的局部变量
|||
|-|-|
|TypeName|AvoidExcessiveLocals|
|CheckId|CA1809|
|类别|Microsoft.Performance|
|是否重大更改|非重大|

## <a name="cause"></a>原因
 成员包含 64 个以上的本地变量，其中一些可能是编译器生成。

## <a name="rule-description"></a>规则说明
 性能优化常见方法是将值存储于处理器寄存器，而不是在内存中，这被称为*注册*值。 公共语言运行时最多可考虑最多为 64 个局部变量。 变量不能放在堆栈上，并且必须转移到之前操作的寄存器。 若要允许出现的机会，所有的局部变量都，限制为 64 本地变量的数目。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复与此规则的冲突，重构要使用局部变量不能超过 64 个的实现。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果性能不是问题，它是安全地禁止显示此规则的警告，或者禁用此规则。

## <a name="related-rules"></a>相关的规则
 [CA1804：移除未使用的局部变量](../code-quality/ca1804-remove-unused-locals.md)