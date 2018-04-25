---
title: QueryCounters | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 8059d4b2-af61-4a47-a6c2-8da5c0741c74
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 64bcd93e6d9045558c231c3b47ff967ffe14c078
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2018
---
# <a name="querycounters"></a>QueryCounters
“QueryCounters”选项列出计算机上可用的 CPU（硬件）性能计数器。  
  
 “QueryCounters”必须是命令行中的唯一选项。  
  
## <a name="syntax"></a>语法  
  
```  
VSPerfCmd.exe /QueryCounters  
```  
  
#### <a name="parameters"></a>参数  
 无  
  
## <a name="remarks"></a>备注  
 使用检测方法时，探查器可以在每个数据收集事件中收集一个或多个 CPU 性能计数器的值。 使用采样分析方法时，可以指定一个计数器事件和要用作采样间隔的事件发生数。  
  
 不同的处理器公开不同的 CPU 性能计数器。 探查器定义一组可用于几乎所有处理器的常规计数器。 “QueryCounters”选项同时列出常规计数器的名称和特定于处理器的计数器名称。  
  
## <a name="see-also"></a>请参阅  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [分析独立应用程序](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [分析 ASP.NET Web 应用程序](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [分析服务](../profiling/command-line-profiling-of-services.md)