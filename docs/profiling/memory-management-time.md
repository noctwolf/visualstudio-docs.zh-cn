---
title: 内存管理时间 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.paging
helpviewer_keywords:
- Concurrency Visualizer, Paging Time
ms.assetid: 67af3509-3a7d-435d-bc37-5262448da915
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6741aa96941e9265ab414ea7d73bb614ace6f9b8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53913947"
---
# <a name="memory-management-time"></a>内存管理时间
时间线中的这些段与归类为内存管理的阻塞时间关联。 此方案意味着线程被与内存管理操作（如分页）关联的事件所阻止。 在此时间内，线程被阻止在并发可视化工具视为内存管理的 API 或内核状态下。 这些包括诸如分页和内存分配这类事件。  
  
 检查关联的调用堆栈和分析报告，以便更好地了解归类为内存管理的阻塞的基本原因。  
  
## <a name="see-also"></a>请参阅  
 [线程视图](../profiling/threads-view-parallel-performance.md)