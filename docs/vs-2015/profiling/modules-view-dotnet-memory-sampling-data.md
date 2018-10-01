---
title: “模块”视图 - .NET 内存采样数据 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Modules view
ms.assetid: 9c05b51a-8382-44cf-a8f7-3fabdd2e8f1b
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f1596d85e2668090533df9021c964d6767d36b38
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476600"
---
# <a name="modules-view---net-memory-sampling-data"></a>“模块”视图 - .NET 内存采样数据
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[模块视图-.NET 内存采样数据](https://docs.microsoft.com/visualstudio/profiling/modules-view-dotnet-memory-sampling-data)。  
  
使用采样方法收集的 .NET 内存分配数据的“模块”视图按分析运行期间执行的模块对内存数据进行分组。 每个模块都是一个层次结构树的根。 模块的各函数在模块节点下列出。  
  
 分配内存的语句的源文件行号在 函数节点下列出，执行分配的指令的地址在行节点下列出。 非独占和独占值始终对于行数据和指令数据始终是相同的。  
  
|列|描述|  
|------------|-----------------|  
|**名称**|模块、函数、行号或指令地址的名称。|  
|**进程 ID**|分析运行的进程 ID (PID)。|  
|**进程名**|进程的名称。|  
|**模块名**|函数所在模块的名称。|  
|**模块路径**|模块的路径。|  
|**源文件**|此函数的定义所在的源文件。|  
|**函数行号**|此函数在源文件中的起始行号。|  
|**非独占分配数**|-   对于函数，是此函数创建的对象的总数。 此数值包括此函数调用的函数中创建的对象数。<br />-   对于模块，是分析运行期间在执行此模块中的至少一个函数时分配的对象的数量。 此数值包括模块函数调用的函数中创建的对象数。<br />-   对于行或指令，是此行或指令分配的对象的总数。|  
|**非独占分配数百分比**|分析运行期间分配的属于模块、函数、行或指令的非独占分配的所有对象数的百分比。|  
|**独占分配数**|-   对于当前函数，是函数执行函数体的代码时（即函数位于调用堆栈顶部时）创建的对象数。 此数值不包括此函数调用的函数中创建的对象数。<br />-   对于模块，是此模块中函数的独占分配之和。<br />-   对于行或指令，是此行或指令创建的对象的总数。|  
|**独占分配数百分比**|分析运行期间分配的属于模块、函数、行或指令的独占分配的所有对象数的百分比。|  
|**非独占字节数**|-   对于函数，是此函数分配的字节数。 此数值包括此函数调用的函数中分配的字节数。<br />-   对于模块，是分析运行期间在执行此模块中的至少一个函数时分配的字节数。 此数值包括模块函数调用的所有函数中创建的对象数。<br />-   对于行或指令，是此行或指令创建的对象的总数。|  
|**非独占字节数百分比**|分析运行期间分配的属于模块、函数、行或指令的非独占字节的所有字节数的百分比。|  
|**独占字节数**|-   对于函数，是此函数分配的字节总数。 此数值不包括此函数调用的函数中分配的字节数。<br />-   对于模块，是此模块中函数分配的独占字节数之和。<br />-   对于行或指令，是此行或指令分配的对象的总数。|  
|**独占字节数百分比**|分析运行期间分配的属于模块、函数、行或指令的独占字节的所有字节数的百分比。|  
  
## <a name="see-also"></a>请参阅  
 [如何：自定义报告视图列](../profiling/how-to-customize-report-view-columns.md)   
 [“模块”视图 - 检测](../profiling/modules-view-dotnet-memory-instrumentation-data.md)   
 [“模块”视图](../profiling/modules-view-sampling-data.md)   
 [“模块”视图](../profiling/modules-view-instrumentation-data.md)



