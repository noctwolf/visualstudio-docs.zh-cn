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
ms.openlocfilehash: 0135241e81fb020d5f5107bcb76e37bad16fb56d
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49828502"
---
# <a name="ca1809-avoid-excessive-locals"></a>CA1809：避免过多的局部变量

|||
|-|-|
|TypeName|AvoidExcessiveLocals|
|CheckId|CA1809|
|类别|Microsoft.Performance|
|是否重大更改|非换行|

## <a name="cause"></a>原因
 成员包含 64 个以上的本地变量，其中一些可能是编译器生成。

## <a name="rule-description"></a>规则说明
 优化性能的常见是将值存储于处理器寄存器，而不是在内存中，这被称为*注册*值。 公共语言运行时最多可考虑最多为 64 个局部变量。 放置在堆栈上的不是以内的变量，必须将移动到操作之前注册。 若要允许可能性，所有本地变量获取以内，限制为 64 的本地变量的数目。

## <a name="how-to-fix-violations"></a>如何解决冲突
 若要修复此规则的冲突，请重构要使用局部变量不能超过 64 个的实现。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 如果性能不是一个问题，是若要禁止显示此规则的警告，或若要禁用规则，安全的。

## <a name="related-rules"></a>相关的规则
 [CA1804：移除未使用的局部变量](../code-quality/ca1804-remove-unused-locals.md)