---
title: I-O 时间（“线程”视图）| Microsoft Docs
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
- vs.cv.threads.timeline.io
helpviewer_keywords:
- Concurrency Visualizer, I/O time (Threads View)
ms.assetid: 0c4ec14d-d8dd-49c1-999c-dcbf4e8e1dc8
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab10b52052ddacb005668a2620846f618e45bc62
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51808591"
---
# <a name="io-time-threads-view"></a>I/O 时间（“线程”视图）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

时间线中的这些段与归类为 I/O 的阻塞时间关联。 这意味着一个线程正在等待 I/O 操作完成。 此线程可能已在 API 中被阻止，或由将并发可视化工具视为 I/O 的 I/O 相关内核等待阻止。 此组中包括 `CreateFile()`、`ReadFile()` 和 `WSARecv()` 等 API。  
  
## <a name="see-also"></a>请参阅  
 [线程视图](../profiling/threads-view-parallel-performance.md)



