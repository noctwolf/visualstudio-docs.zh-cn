---
title: CA1600： 不要使用 idle 进程优先级 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DoNotUseIdleProcessPriority
- CA1600
helpviewer_keywords:
- CA1600
- DoNotUseIdleProcessPriority
ms.assetid: 9b0d073b-78b6-41be-8ef3-14692a735283
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b211c1ab646d27cf32290d3c5c306719ba7decff
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2018
ms.locfileid: "47587782"
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600：不要使用 Idle 进程优先级
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[CA1600： 不要使用 idle 进程优先级](https://docs.microsoft.com/visualstudio/code-quality/ca1600-do-not-use-idle-process-priority)。

|||
|-|-|
|TypeName|DoNotUseIdleProcessPriority|
|CheckId|CA1600|
|类别|Microsoft.Mobility|
|是否重大更改|重大|

## <a name="cause"></a>原因
 当进程设置为时将引发此规则`ProcessPriorityClass.Idle`。

## <a name="rule-description"></a>规则说明
 不要将进程优先级设置为 Idle。 进程`System.Diagnostics.ProcessPriorityClass.Idle`它本应处于空闲状态，并因此将阻止进入待机状态时占用 CPU。

## <a name="how-to-fix-violations"></a>如何解决冲突
 设置为进程`ProcessPriorityClass.BelowNormal`。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 仅当 Idle 进程优先级是必需的且可以安全地忽略移动性注意事项时，应禁止显示此规则。



