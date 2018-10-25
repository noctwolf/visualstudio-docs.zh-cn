---
title: 同步时间 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.synchronization
helpviewer_keywords:
- Concurrency Visualizer, Synchronization Time
ms.assetid: affa04cc-8bba-4848-9301-b19846d3c2cb
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 12be885a79daa3ba5531f6da9652d6a9708b3c96
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49826994"
---
# <a name="synchronization-time"></a>同步时间
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

时间线中的这些段与归类为同步的阻止时间关联。 当线程被标记为在同步中阻止时，表示出现了下列情况之一：  
  
- 执行该线程可能会导致调用已知线程同步 API（如 `EnterCriticalSection()` 或 `WaitForSingleObject()`）。  
  
- API 匹配算法无法做到非常全面，因此一些可映射到其他类别的 API 也可能显示为同步，这是因为调用堆栈中的帧会最终到达映射到此类别的基础内核阻止基元。  
  
  若要了解线程阻止事件的基本原因，可仔细检查阻止调用堆栈和分析报告。  
  
## <a name="see-also"></a>请参阅  
 [线程视图](../profiling/threads-view-parallel-performance.md)



