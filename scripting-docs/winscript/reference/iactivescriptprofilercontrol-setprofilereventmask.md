---
title: IActiveScriptProfilerControl::SetProfilerEventMask |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerControl.SetProfilerEventMask
apilocation:
- scrobj.dll
ms.assetid: 207e192f-e12e-4fcb-b4d8-eaee50ecb86e
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 45ded6caec95f5421328be09e299af535765a9c2
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086783"
---
# <a name="iactivescriptprofilercontrolsetprofilereventmask"></a>IActiveScriptProfilerControl::SetProfilerEventMask
设置指定的脚本引擎应引发的事件类型的 4 字节位掩码。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT SetProfilerEventMask(  
    [in] DWORD dwEventMask);  
```  
  
#### <a name="parameters"></a>参数  
 `dwEventMask`  
 [in]4 字节位掩码，用于指定事件的类型。 在中定义 bits [PROFILER_EVENT_MASK 枚举](../../winscript/reference/profiler-event-mask-enumeration.md)。  
  
## <a name="return-value"></a>返回值  
 返回一个 HRESULT。 可能的值如下：  
  
|返回值|含义|  
|------------------|-------------|  
|`S_OK`|方法成功。|  
|`ACTIVPROF_E_PROFILER_ABSENT`|未启用分析。|  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptProfilerControl 接口](../../winscript/reference/iactivescriptprofilercontrol-interface.md)