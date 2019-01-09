---
title: IActiveScriptErrorDebug::GetStackFrame |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptErrorDebug.GetStackFrame
apilocation:
- jscript.dll
helpviewer_keywords:
- IActiveScriptErrorDebug::GetStackFrame
ms.assetid: a6f43102-68c5-46f5-a4df-fa3aaf53a967
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b9331738c52453f4ef80b70ab7eebd79907d1f54
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094128"
---
# <a name="iactivescripterrordebuggetstackframe"></a>IActiveScriptErrorDebug::GetStackFrame
提供了适用于运行时错误的堆栈帧。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetStackFrame(  
   IDebugStackFrame**  ppdsf  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppdsf`  
 [out]错误堆栈帧。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法提供了适用于运行时错误的堆栈帧。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptErrorDebug 接口](../../winscript/reference/iactivescripterrordebug-interface.md)