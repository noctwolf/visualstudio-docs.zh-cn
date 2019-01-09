---
title: IActiveScriptProfilerControl::StartProfiling |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerControl.StartProfiling
apilocation:
- scrobj.dll
ms.assetid: 56a7b3b7-8c21-43d0-9d8b-53bbc19fabb9
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3a64bbb790933513d29ee1a534472ac92c2072cf
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088291"
---
# <a name="iactivescriptprofilercontrolstartprofiling"></a>IActiveScriptProfilerControl::StartProfiling
启动脚本引擎的分析。 脚本引擎通过调用创建探查器对象的实例[CoCreateInstance](https://docs.microsoft.com/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance)。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT StartProfiling(  
    [in] REFCLSID clsidProfilerObject,  
    [in] DWORD dwEventMask,  
    [in] DWORD dwContext);  
```  
  
#### <a name="parameters"></a>参数  
 `clsidProfilerObject`  
 [in]类标识符 (CLSID) 要创建的探查器对象。  
  
 `dwEventMask`  
 [in]4 字节位掩码，用于指定事件的类型。 在中定义 bits [PROFILER_EVENT_MASK 枚举](../../winscript/reference/profiler-event-mask-enumeration.md)。  
  
 `dwContext`  
 [in]一个 4 字节值，该值传递给探查器对象。  
  
## <a name="return-value"></a>返回值  
 返回一个 HRESULT。 可能的值如下：  
  
|返回值|含义|  
|------------------|-------------|  
|`S_OK`|方法成功。|  
|`ACTIVPROF_E_PROFILER_PRESENT`|已启用分析。|  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptProfilerControl 接口](../../winscript/reference/iactivescriptprofilercontrol-interface.md)