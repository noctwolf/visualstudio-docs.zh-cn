---
title: diagnostic 命名空间 | Microsoft Docs
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
- cvmarkersobj/Concurrency::diagnostic
helpviewer_keywords:
- Concurrency::diagnostic namespace
ms.assetid: ad786b19-7c4c-46ee-bfb6-c4752b373a09
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3959d7f5399073e3d27131ffcd73541c882d9cdd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471637"
---
# <a name="diagnostic-namespace"></a>diagnostic 命名空间
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[诊断 Namespace](https://docs.microsoft.com/visualstudio/profiling/diagnostic-namespace)。  
  
`diagnostics` 命名空间提供用于发出并行可视化工具标记的功能。  
  
## <a name="syntax"></a>语法  
  
```  
namespace diagnostic;  
```  
  
## <a name="members"></a>成员  
  
### <a name="classes"></a>类  
  
|名称|描述|  
|----------|-----------------|  
|[marker_series 类](../profiling/marker-series-class.md)|表示由单个提供程序生成的一系列事件通道。|  
|[span 类](../profiling/span-class.md)|定义应用程序的一个阶段。|  
  
### <a name="enumerations"></a>枚举  
  
|name|描述|  
|----------|-----------------|  
|[marker_importance 枚举](../profiling/marker-importance-enumeration.md)|表示并发可视化工具标记的重要性级别。|  
  
## <a name="requirements"></a>要求  
 **标头：** cvmarkersobj.h  
  
 **命名空间：** 并发  
  
## <a name="see-also"></a>请参阅  
 [Concurrency 命名空间（并发可视化工具）](../profiling/concurrency-namespace-concurrency-visualizer.md)



