---
title: I-O 时间（“线程”视图）| Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.cv.threads.timeline.io
helpviewer_keywords:
- Concurrency Visualizer, I/O time (Threads View)
ms.assetid: 0c4ec14d-d8dd-49c1-999c-dcbf4e8e1dc8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 253aa8c3a8ca5161fbb95e18f38f0ff232cd37bc
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2018
ms.locfileid: "34844841"
---
# <a name="io-time-threads-view"></a>I/O 时间（“线程”视图）
时间线中的这些段与归类为 I/O 的阻塞时间关联。 这意味着一个线程正在等待 I/O 操作完成。 此线程可能已在 API 中被阻止，或由将并发可视化工具视为 I/O 的 I/O 相关内核等待阻止。 此组中包括 `CreateFile()`、`ReadFile()` 和 `WSARecv()` 等 API。  
  
## <a name="see-also"></a>请参阅  
 [线程视图](../profiling/threads-view-parallel-performance.md)