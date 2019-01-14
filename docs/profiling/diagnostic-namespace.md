---
title: diagnostic 命名空间 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkersobj/Concurrency::diagnostic
helpviewer_keywords:
- Concurrency::diagnostic namespace
ms.assetid: ad786b19-7c4c-46ee-bfb6-c4752b373a09
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c46f67281fe62de36472d9007f21841e843c20fa
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53839438"
---
# <a name="diagnostic-namespace"></a>diagnostic 命名空间
`diagnostics` 命名空间提供用于发出并行可视化工具标记的功能。  
  
## <a name="syntax"></a>语法  
  
```cpp  
namespace diagnostic;  
```  
  
## <a name="members"></a>成员  
  
### <a name="classes"></a>类  
  
|name|说明|  
|----------|-----------------|  
|[marker_series 类](../profiling/marker-series-class.md)|表示由单个提供程序生成的一系列事件通道。|  
|[span 类](../profiling/span-class.md)|定义应用程序的一个阶段。|  
  
### <a name="enumerations"></a>枚举  
  
|name|说明|  
|----------|-----------------|  
|[marker_importance 枚举](../profiling/marker-importance-enumeration.md)|表示并发可视化工具标记的重要性级别。|  
  
## <a name="requirements"></a>要求  
 **标头：** cvmarkersobj.h  
  
 **命名空间：** 并发  
  
## <a name="see-also"></a>请参阅  
 [Concurrency 命名空间（并发可视化工具）](../profiling/concurrency-namespace-concurrency-visualizer.md)