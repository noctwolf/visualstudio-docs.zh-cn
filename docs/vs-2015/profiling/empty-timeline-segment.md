---
title: 空时间线分段 | Microsoft Docs
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
- vs.cv.threads.timeline.empty
helpviewer_keywords:
- Concurrency Visualizer, empty timeline segment
ms.assetid: f37b301f-3edc-4e56-8084-feec2dc5a9b1
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 64ff71dca6a4a590551909dc05357b80da32e18c
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51739862"
---
# <a name="empty-timeline-segment"></a>空时间线分段
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在并发可视化工具中，时间线部分为空（具有白色背景）的原因取决于通道的种类。  
  
-   对于 CPU 线程通道，这意味着在时间线的这一部分，线程不存在。 如果您需要查看线程，则可以使用缩放控件或通过水平滚动来查找其执行部分。  
  
-   对于 I/O 通道，这意味着在该时间点未代表目标进程发生磁盘访问。  
  
-   对于 DirectX 通道，这意味着在时间线的这一部分，未代表目标进程执行任何 GPU 工作。  
  
-   对于标记通道，这意味着未生成任何标记。  
  
## <a name="see-also"></a>请参阅  
 [“线程”视图](../profiling/threads-view-parallel-performance.md)   
 [缩放控件（“线程”视图）](../profiling/zoom-control-threads-view.md)



