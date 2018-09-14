---
title: CA1601：不要使用阻止电源状态更改的计时器
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
helpviewer_keywords:
- CA1601
- DoNotUseTimersThatPreventPowerStateChanges
ms.assetid: b8028c92-0696-4c54-9773-0028f29bda9a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 033c7a73c404a2bd5146a17a1a7b4f2fa8b9c540
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45545708"
---
# <a name="ca1601-do-not-use-timers-that-prevent-power-state-changes"></a>CA1601：不要使用阻止电源状态更改的计时器
|||
|-|-|
|TypeName|DoNotUseTimersThatPreventPowerStateChanges|
|CheckId|CA1601|
|类别|Microsoft.Mobility|
|是否重大更改|重大|

## <a name="cause"></a>原因
 计时器的频率设置为每秒超过一次。

## <a name="rule-description"></a>规则说明
 不执行通常比一次每秒或发生的频率高于一个使用计时器轮询每秒的时间。 频率较高的定期活动会使 CPU 处于繁忙状态，并且会干扰具有节能功能（关闭显示器和硬盘）的空闲计时器。

## <a name="how-to-fix-violations"></a>如何解决冲突
 设置计时器间隔发生每秒不超过一次。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 应禁止显示此规则，仅当是必需的触发计时器每秒超过一次且可以安全地忽略移动性注意事项。