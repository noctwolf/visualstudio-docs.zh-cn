---
title: GPU 活动关系图 | Microsoft Docs
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
- vs.cv.cpu.graph.gpu
ms.assetid: d7c769af-95fb-49a3-b5ab-deafecee46fa
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d5a0ef828b221219c3abae0e46ec40d21b6b045c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482249"
---
# <a name="gpu-activity-graph"></a>GPU 活动关系图
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[GPU 活动关系图](https://docs.microsoft.com/visualstudio/profiling/gpu-activity-graph)。  
  
并发可视化工具中的 GPU 活动图显示系统上的 DirectX 活动级别，此活动级别通过一段时间内使用的 DirectX 引擎数来衡量。  此图不显示使用了哪些特定引擎。  如果引擎正在处理任意 GPU 工作，则将视为正在使用此引擎。  
  
## <a name="gpu-activity-graph-colors"></a>GPU 活动图颜色  
 绿色表示当前进程使用的 DirectX 引擎数。  
  
 浅灰色表示系统上其他进程使用的 DirectX 引擎数。 若要减少其他进程使用的 DirectX 引擎数，请减少系统上运行的其他进程数。  
  
 白色表示系统上未使用的 DirectX 引擎的可用性。 如果可以找到更多利用机会，这些引擎就可以用于您的进程。 一些引擎只能用于特定种类的任务。  
  
## <a name="see-also"></a>请参阅  
 [使用率视图](../profiling/utilization-view.md)



