---
title: IActiveScriptSiteDebug::OnScriptErrorDebug |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteDebug.OnScriptErrorDebug
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteDebug::OnScriptErrorDebug
ms.assetid: 87f201da-36eb-49a2-b000-e1e1e8c4cdb7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5680d22ffa5ec648afaced5e98f651e35758f929
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092113"
---
# <a name="iactivescriptsitedebugonscripterrordebug"></a>IActiveScriptSiteDebug::OnScriptErrorDebug
允许智能主机以确定如何处理运行时错误。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT OnScriptErrorDebug(  
   IActiveScriptErrorDebug*  pErrorDebug,  
   BOOL*                     pfEnterDebugger,  
   BOOL*                     pfCallOnScriptErrorWhenContinuing  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pErrorDebug`  
 [in]发生的运行时错误  
  
 `pfEnterDebugger`  
 [out]指示是否将错误传递给调试程序执行 JIT 调试标记。  
  
 `pfCallOnScriptErrorWhenContinuing`  
 [out]指示是否将调用`IActiveScriptSite::OnScriptError`当用户决定继续而不进行调试。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括但不限于以下表中的值。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 智能主机可以使用此方法来确定如何处理运行时错误。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptSiteDebug 接口](../../winscript/reference/iactivescriptsitedebug-interface.md)