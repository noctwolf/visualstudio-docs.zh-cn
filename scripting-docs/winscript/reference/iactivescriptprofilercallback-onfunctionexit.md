---
title: IActiveScriptProfilerCallback::OnFunctionExit |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.OnFunctionExit
apilocation:
- scrobj.dll
ms.assetid: a5d21715-2b0b-423e-8644-f04a9e7cde3d
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb3f71e9a8a383e2362bacb17698f4eec58f464e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092193"
---
# <a name="iactivescriptprofilercallbackonfunctionexit"></a>IActiveScriptProfilerCallback::OnFunctionExit
通知探查器对象，脚本引擎已完成执行函数调用不是调用到文档对象模型 (DOM)。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT OnFunctionExit(  
    [in] PROFILER_TOKEN scriptId,   
    [in] PROFILER_TOKEN functionId);  
```  
  
#### <a name="parameters"></a>参数  
 `scriptId`  
 [in]该脚本，该函数属于的唯一 ID。 由脚本引擎分配此 ID。  
  
 `functionId`  
 [in]函数的唯一 ID。 由脚本引擎分配此 ID。  
  
## <a name="return-value"></a>返回值  
 此方法的返回值是脚本引擎忽略。  
  
## <a name="remarks"></a>备注  
 对于 DOM 调用，脚本引擎将调用[IActiveScriptProfilerCallback2::OnFunctionExitByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionexitbyname.md)而不是`IActiveScriptProfilerCallback::OnFunctionExit`。 这是由于大量的唯一方法和属性的数组。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptProfilerCallback::OnFunctionEnter](../../winscript/reference/iactivescriptprofilercallback-onfunctionenter.md)   
 [IActiveScriptProfilerCallback 接口](../../winscript/reference/iactivescriptprofilercallback-interface.md)