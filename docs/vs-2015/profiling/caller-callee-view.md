---
title: “调用方-被调用方”视图 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.callercallee
helpviewer_keywords:
- profiling tools, reports, Caller/Callee view
- profiling tools, Caller/Callee view
- performance reports, Caller/Callee view
- Caller/Callee view
ms.assetid: d3511bcf-cce0-4cbe-aecb-b94c7c80ad1b
caps.latest.revision: 37
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 58aca542571066ecfa9328c9600972665e757150
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "68176633"
---
# <a name="callercallee-view"></a>“调用方/被调用方”视图
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

“调用方/被调用方”视图显示所选函数及其父函数和子函数的分析信息。 “调用方/被调用方”视图包含三个网格：  
  
 **当前函数**在中间网格中显示，其显示所选函数的分析信息。 值包括对分析运行期间收集的函数的所有调用。  
  
 **调用当前函数的函数**在顶部网格中显示，并且显示由调用方（父）函数的调用生成的所选（当前）函数的值的数量。  
  
 **由当前函数调用的函数**在底部网格中显示，当前函数调用子函数时，它会显示所选函数的被调用方（子）函数的分析信息。  
  
 “调用方/被调用方”视图中的可用列取决于用于收集数据的分析方法（采样法或检测法）以及是否在分析运行期间收集 .NET 内存数据。  
  
 双击视图其他两部分中列出的任意一个函数，可选择其他函数作为“报表”视图中间部分中的“当前函数”。 会自动更新“报表”视图以反映更改。  
  
 可通过单击列名对数据进行排序。 可将其他列添加到“调用方/被调用方”视图。 有关详细信息，请参阅[如何：自定义报告视图列](../profiling/how-to-customize-report-view-columns.md)。  
  
## <a name="see-also"></a>请参阅  
 [“调用方/被调用方”视图 - 采样数据](../profiling/caller-callee-view-sampling-data.md)   
 [“调用方/被调用方”视图 - 检测数据](../profiling/caller-callee-view-instrumentation-data.md)   
 [“调用方/被调用方”视图 - .NET 内存检测数据](../profiling/caller-callee-view-net-memory-instrumentation-data.md)   
 [“调用方/被调用方”视图 - .NET 内存采样数据](../profiling/caller-callee-view-dotnet-memory-sampling-data.md)   
 [“调用方/被调用方”视图 - 争用数据](../profiling/caller-callee-view-contention-data.md)
