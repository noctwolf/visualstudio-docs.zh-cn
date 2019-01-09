---
title: IActiveScriptProfilerCallback::FunctionCompiled |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProfilerCallback.FunctionCompiled
apilocation:
- scrobj.dll
ms.assetid: a7e9ef17-3891-4731-9d08-c37bc489be61
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4bd032914605c61b13a0a56a42e510c2af252f7e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091398"
---
# <a name="iactivescriptprofilercallbackfunctioncompiled"></a>IActiveScriptProfilerCallback::FunctionCompiled
通知探查器对象的脚本引擎编译脚本时遇到一个函数。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT FunctionCompiled(  
    [in] PROFILER_TOKEN functionId,  
    [in] PROFILER_TOKEN scriptId,  
    [in] [string] const WCHAR *pwszFunctionName,  
    [in] [string] const WCHAR *pwszFunctionNameHint,  
    [in] IUnknown *pIDebugDocumentContext);  
```  
  
#### <a name="parameters"></a>参数  
 `functionId`  
 [in]函数的唯一 ID。 由脚本引擎分配此 ID。  
  
 `scriptId`  
 [in]该脚本，该函数属于的唯一 ID。  
  
 `pwszFunctionName`  
 [in]匿名函数的函数或为空的名称。  
  
 `pwszFunctionNameHint`  
 [in]推断的函数或如果脚本引擎未推断任何名称，则为 null 的名称。  
  
 `pIDebugDocumentContext`  
 [in]如果可用，指向`IUnknown`探查器必须查询接口[IDebugDocumentContext 接口](../../winscript/reference/idebugdocumentcontext-interface.md)指针。 否则为 null。  
  
## <a name="return-value"></a>返回值  
 此方法的返回值是脚本引擎忽略。  
  
## <a name="remarks"></a>备注  
 仅当主机支持此功能，脚本引擎可以提供文档上下文。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptProfilerCallback 接口](../../winscript/reference/iactivescriptprofilercallback-interface.md)