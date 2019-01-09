---
title: PROFILER_EVENT_MASK 枚举 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- PROFILER_EVENT_MASK
apilocation:
- scrobj.dll
ms.assetid: c2168408-f4f6-4600-971d-f15b4edf4ca2
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: da55371c24f6a21acbc9dc789a2c76ef6e7c66b4
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096663"
---
# <a name="profilereventmask-enumeration"></a>PROFILER_EVENT_MASK 枚举
指示应进行事件探查的事件的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp
typedef enum {  
    PROFILER_EVENT_MASK_TRACE_SCRIPT_FUNCTION_CALL = 0x00000001,  
    PROFILER_EVENT_MASK_TRACE_NATIVE_FUNCTION_CALL = 0x00000002,  
    PROFILER_EVENT_MASK_TRACE_DOM_FUNCTION_CALL    = 0x00000004,  
    PROFILER_EVENT_MASK_TRACE_ALL =  
    PROFILER_EVENT_MASK_TRACE_SCRIPT_FUNCTION_CALL |  
    PROFILER_EVENT_MASK_TRACE_NATIVE_FUNCTION_CALL,  
    PROFILER_EVENT_MASK_TRACE_ALL_WITH_DOM = PROFILER_EVENT_MASK_TRACE_ALL |  
    PROFILER_EVENT_MASK_TRACE_DOM_FUNCTION_CALL  
} PROFILER_EVENT_MASK;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|PROFILER_EVENT_MASK_TRACE_SCRIPT_FUNCTION_CALL|配置文件在用户编写脚本和动态代码中定义的函数。|  
|PROFILER_EVENT_MASK_TRACE_NATIVE_FUNCTION_CALL|配置文件定义的脚本引擎的本机函数。|  
|PROFILER_EVENT_MASK_TRACE_ALL|配置文件不包括调用到文档对象模型 (DOM) 的所有用户定义和脚本引擎函数。|  
|PROFILER_EVENT_MASK_TRACE_DOM_FUNCTION_CALL|配置文件函数调用到 dom 中。|  
|PROFILER_EVENT_MASK_TRACE_ALL_WITH_DOM|配置文件的所有功能，包括调入 dom。|  
  
## <a name="see-also"></a>请参阅  
 [活动脚本 Profiler 常量、 枚举和结构](../../winscript/reference/active-script-profiler-constants-enumerations-and-structures.md)   
 [IActiveScriptProfilerControl::SetProfilerEventMask](../../winscript/reference/iactivescriptprofilercontrol-setprofilereventmask.md)   
 [IActiveScriptProfilerControl::StartProfiling](../../winscript/reference/iactivescriptprofilercontrol-startprofiling.md)