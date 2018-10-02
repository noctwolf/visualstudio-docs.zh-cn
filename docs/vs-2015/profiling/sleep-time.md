---
title: 睡眠时间 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.threads.timeline.sleep
helpviewer_keywords:
- Concurrency Visualizer, Sleep Time
ms.assetid: 3ddb96f9-9bda-4a68-ad4d-ef488a0a68dc
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd4d12097a8bf952cc0af0fa99025b9747ee7b3f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482758"
---
# <a name="sleep-time"></a>睡眠时间
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[休眠时间](https://docs.microsoft.com/visualstudio/profiling/sleep-time)。  
  
时间线中的这些时间段与归类为睡眠的阻塞时间关联。 睡眠类别意味着某线程自动放弃其逻辑内核并且不执行任何工作。 在此时间内，线程已在被并发可视化工具计数为睡眠的 API 中阻塞。 `Sleep()` 和 `SwitchToThread()` 等 API 就归为此组。  
  
## <a name="see-also"></a>请参阅  
 [线程视图](../profiling/threads-view-parallel-performance.md)



