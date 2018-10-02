---
title: “核心”视图 | Microsoft Docs
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
- vs.performance.view.cores
helpviewer_keywords:
- Concurrency Visualizer, Cores View
ms.assetid: e47af672-9785-4899-bd45-4d9dda3c396f
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bce1c1ca458b8d06af89c669a76a2a93371fad5a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476577"
---
# <a name="cores-view"></a>内核视图
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[核心视图](https://docs.microsoft.com/visualstudio/profiling/cores-view)。  
  
内核视图显示线程执行如何映射到逻辑处理器内核。 如果要编写服务器应用程序，则此视图可以帮助您通过使用线程关联或线程池管理来优化缓存性能。 如果在使用线程关联之后实际上加剧了跨核迁移问题，则此视图还可帮助您以直观方式检查相关情况。 内核视图包括关系图和图例两个部分。  
  
 关系图在 Y 轴上显示逻辑内核，而在 X 轴上显示时间。 关系图中的每个线程都具有唯一的颜色，以便您可以跟踪它随时间跨核心移动的情况。 通过在图例区域中选择线程，您可以在此关系图中筛选它们。  
  
 图例区域中具有关系图中每种颜色的对应项。 每个项各自显示线程颜色和名称、跨核心上下文切换数、上下文切换的总数，以及跨越核心的上下文切换所占的百分比。 图例按跨核心的上下文切换数以降序排序。 它仅会列出在显示的时间范围内执行的线程。  缩放或平移后，将更新列表。  
  
## <a name="see-also"></a>请参阅  
 [并发可视化工具](../profiling/concurrency-visualizer.md)   
 [使用率视图](../profiling/utilization-view.md)   
 [线程视图](../profiling/threads-view-parallel-performance.md)



