---
title: 睡眠时间 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.sleep
helpviewer_keywords:
- Concurrency Visualizer, Sleep Time
ms.assetid: 3ddb96f9-9bda-4a68-ad4d-ef488a0a68dc
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 8a79bbca9f6275f115105cc2ba6b001ac0ca7d44
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54774615"
---
# <a name="sleep-time"></a>睡眠时间
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

时间线中的这些时间段与归类为睡眠的阻塞时间关联。 睡眠类别意味着某线程自动放弃其逻辑内核并且不执行任何工作。 在此时间内，线程已在被并发可视化工具计数为睡眠的 API 中阻塞。 `Sleep()` 和 `SwitchToThread()` 等 API 就归为此组。  
  
## <a name="see-also"></a>请参阅  
 [线程视图](../profiling/threads-view-parallel-performance.md)
