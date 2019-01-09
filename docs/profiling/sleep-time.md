---
title: 睡眠时间 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.sleep
helpviewer_keywords:
- Concurrency Visualizer, Sleep Time
ms.assetid: 3ddb96f9-9bda-4a68-ad4d-ef488a0a68dc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 53f9137c35bd89e812f1d671e2e51f88b343753c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53920253"
---
# <a name="sleep-time"></a>睡眠时间
时间线中的这些时间段与归类为睡眠的阻塞时间关联。 睡眠类别意味着某线程自动放弃其逻辑内核并且不执行任何工作。 在此时间内，线程已在被并发可视化工具计数为睡眠的 API 中阻塞。 `Sleep()` 和 `SwitchToThread()` 等 API 就归为此组。  
  
## <a name="see-also"></a>请参阅  
 [“线程”视图](../profiling/threads-view-parallel-performance.md)