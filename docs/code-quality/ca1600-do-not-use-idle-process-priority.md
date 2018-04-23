---
title: CA1600：不要使用 Idle 进程优先级
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotUseIdleProcessPriority
- CA1600
helpviewer_keywords:
- CA1600
- DoNotUseIdleProcessPriority
ms.assetid: 9b0d073b-78b6-41be-8ef3-14692a735283
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d052d2e6d9e3b47217cc6ce25fe752e0e2859437
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600：不要使用 Idle 进程优先级
|||
|-|-|
|TypeName|DoNotUseIdleProcessPriority|
|CheckId|CA1600|
|类别|Microsoft.Mobility|
|是否重大更改|重大|

## <a name="cause"></a>原因
 进程被设置为时，将引发此规则`ProcessPriorityClass.Idle`。

## <a name="rule-description"></a>规则说明
 不要将进程优先级设置为 Idle。 进程`System.Diagnostics.ProcessPriorityClass.Idle`将 CPU 时占用它本应处于空闲状态，因此将阻止进入待机状态。

## <a name="how-to-fix-violations"></a>如何解决冲突
 设置为进程`ProcessPriorityClass.BelowNormal`。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 仅当需要 Idle 进程优先级也可以安全地忽略移动性注意事项时，应禁止显示此规则。