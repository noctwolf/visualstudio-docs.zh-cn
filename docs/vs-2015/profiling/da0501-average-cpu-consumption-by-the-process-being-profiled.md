---
title: DA0501：所分析的进程的平均 CPU 使用率。 | Microsoft Docs
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
- vs.performance.rules.DA0501
- vs.performance.DA0501
- vs.performance.501
ms.assetid: b01946b4-75e3-47d5-a1a1-cebfae66a3af
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7c9b36521c9d4afec0daba945de415477bcd948
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472390"
---
# <a name="da0501-average-cpu-consumption-by-the-process-being-profiled"></a>DA0501：所分析的进程的平均 CPU 使用率。
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[DA0501： 所分析的进程的平均 CPU 消耗量。](https://docs.microsoft.com/visualstudio/profiling/da0501-average-cpu-consumption-by-the-process-being-profiled)。  
  
规则 Id |DA501 |  
|类别 |资源监视 |  
|分析方法 |所有 |  
|消息 |平均所分析的进程的 CPU 消耗量。 |  
|规则类型 |信息 |  
  
 使用采样法、.NET 内存或资源争用方法进行分析时，必须收集至少 10 个样本才能触发此规则。  
  
## <a name="rule-description"></a>规则说明  
 此消息报告处理器忙于执行应用程序指令的时间的百分比。 报告的值是所分析的进程处于活动状态的所有测量时间间隔的平均值。 具有多个处理器的计算机上的值可能大于 100%。  
  
## <a name="how-to-use-rule-data"></a>如何使用规则数据  
 使用规则值比较程序的不同版本或生成的性能，或了解在不同的测试方案中应用程序的性能。



