---
title: IActiveScriptErrorDebug110::GetExceptionThrownKind |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptErrorDebug110::QueryIsFirstChance
ms.assetid: ecc16e54-93e4-4322-ae13-afa7cd860032
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 61f045348add6ba9595bc93ff48dc2d35498016a
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58145507"
---
# <a name="iactivescripterrordebug110getexceptionthrownkind"></a>IActiveScriptErrorDebug110::GetExceptionThrownKind
返回用于指示已引发异常的类型的值。  
  
> [!IMPORTANT]
>  [IActiveScriptErrorDebug110 接口](../../winscript/reference/iactivescripterrordebug110-interface.md)由 PDM 11.0 和更高版本实现。 在 activdbg100.h 中发现。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetExceptionThrownKind(  
   SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND*  pExceptionKind  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pExceptionKind`  
 [out]（例如，首次异常或未经处理），引发的异常的类型为由[SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND 枚举](../../winscript/reference/script-error-debug-exception-thrown-kind-enumeration.md)枚举值。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptErrorDebug110 接口](../../winscript/reference/iactivescripterrordebug110-interface.md)