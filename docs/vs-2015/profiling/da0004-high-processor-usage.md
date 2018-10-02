---
title: DA0004：处理器使用率很高 | Microsoft Docs
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
- vs.performance.rules.DAHighProcessorUsage
- vs.performance.rules.DA0004
- vs.performance.DA0004
- vs.performance.4
ms.assetid: 2c4fb569-929e-4f1d-8c50-b590ee371351
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 759ba305335c75591bf975e40f011f31edd1bdb5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483994"
---
# <a name="da0004-high-processor-usage"></a>DA0004：处理器使用率很高
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[DA0004： 处理器使用率很高](https://docs.microsoft.com/visualstudio/profiling/da0004-high-processor-usage)。  
  
规则 Id |DA0004 |  
|类别 |分析工具使用情况 |  
|分析方法 |检测采样 |  
|消息 |您的处理器使用率始终高于 75%。 请考虑使用采样模式对 CPU 密集型应用程序。 |  
|规则类型 |信息 |  
  
 使用采样法、.NET 内存或资源争用方法进行分析时，必须收集至少 10 个样本才能触发此规则。  
  
## <a name="cause"></a>原因  
 使用检测方法收集的分析数据中的处理器 (CPU) 使用率非常高。 分析 CPU 密集型应用程序时，请考虑使用采样分析方法。  
  
## <a name="rule-description"></a>规则说明  
 在此分析运行期间，此处理器（或多个处理器）始终处于忙碌状态。 CPU 使用率高可能表示存在 CPU 密集型应用程序。 检测分析方法通常不是调查 CPU 使用情况的最有效方法。 分析花费大量时间在处理器上执行指令的应用程序时，采样法通常更有效。  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
 请考虑使用采样法而非检测法再次分析应用程序，除非需要使用函数计时，或者你更希望了解输入/输出而非处理器瓶颈。




