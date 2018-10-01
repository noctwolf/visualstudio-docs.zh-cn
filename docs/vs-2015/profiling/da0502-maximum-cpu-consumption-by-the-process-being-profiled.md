---
title: DA0502：所分析的进程的 CPU 最大消耗量 | Microsoft Docs
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
- vs.performance.rules.DA0502
- vs.performance.DA0502
- vs.performance.502
ms.assetid: 1ee53df5-b0dc-4265-9d4f-527830d08725
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: be9b9ff318ade6546369e20d5508b2ad79dc0bb9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470965"
---
# <a name="da0502-maximum-cpu-consumption-by-the-process-being-profiled"></a>DA0502：所分析的进程的 CPU 最大消耗量
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[DA0502： 所分析的进程的最大 CPU 消耗量](https://docs.microsoft.com/visualstudio/profiling/da0502-maximum-cpu-consumption-by-the-process-being-profiled)。  
  
规则 Id |DA0502 |  
|类别 |资源监视 |  
|分析方法 |所有 |  
|消息 |此规则仅供参考。 Process()\\% 处理器时间计数器测量正在分析的进程的 CPU 消耗量。 报告的值在所有测量时间间隔观察到最大值。 |  
|规则类型 |信息性 |  
  
 使用采样法、.NET 内存或资源争用方法进行分析时，必须收集至少 10 个样本才能触发此规则。  
  
## <a name="rule-description"></a>规则说明  
 此消息报告处理器忙于执行应用程序指令的时间的最大百分比。 报告的值是所分析的进程在其中处于活动状态的所有测量间隔中报告的最大值。 具有多个处理器的计算机上的百分比可能大于 100%。  
  
## <a name="how-to-use-the-rule-data"></a>如何使用规则数据  
 若要了解不同分析方案中应用程序的性能，可使用规则值比较不同版本程序的性能。



