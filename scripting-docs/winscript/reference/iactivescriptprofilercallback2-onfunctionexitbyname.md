---
title: IActiveScriptProfilerCallback2::OnFunctionExitByName |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptProfilerCallback2::OnFunctionExitByName
ms.assetid: a6ddead4-e66d-4789-b778-84e5c343f908
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb198f56e5ff73561fe7b42a25b019dfb0e3817c
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094557"
---
# <a name="iactivescriptprofilercallback2onfunctionexitbyname"></a>IActiveScriptProfilerCallback2::OnFunctionExitByName
通知探查器的脚本引擎的对象完成运行的文档对象模型 (DOM) 函数调用。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT OnFunctionExitByName(  
    [in] [string] const WCHAR *pwszFunctionName,  
    [in] PROFILER_SCRIPT_TYPE scriptType);  
  
```  
  
#### <a name="parameters"></a>参数  
 `pwszFunctionName`  
 [in]脚本引擎运行完该函数的名称。  
  
 `scriptType`  
 [in]该函数的类型。 有关有效值的说明，请参阅[PROFILER_SCRIPT_TYPE 枚举](../../winscript/reference/profiler-script-type-enumeration.md)。  
  
## <a name="return-value"></a>返回值  
 此方法的返回值是脚本引擎忽略。  
  
## <a name="remarks"></a>备注  
 对于 DOM 调用，脚本引擎调用此方法而不是调用[IActiveScriptProfilerCallback::OnFunctionExit](../../winscript/reference/iactivescriptprofilercallback-onfunctionexit.md)。 这是由于大量的唯一方法和属性的数组。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptProfilerCallback2::OnFunctionEnterByName](../../winscript/reference/iactivescriptprofilercallback2-onfunctionenterbyname.md)   
 [IActiveScriptProfilerCallback2 接口](../../winscript/reference/iactivescriptprofilercallback2-interface.md)