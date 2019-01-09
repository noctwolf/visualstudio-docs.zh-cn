---
title: IActiveScriptSiteInterruptPoll::QueryContinue |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteInterruptPoll.QueryContinue
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteInterruptPoll::QueryContinue
ms.assetid: 41ac3807-f8b4-4a0e-bcc6-556bc89f3904
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9b43211dca57a404d5625cfc2d7ede67a70a0a40
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087979"
---
# <a name="iactivescriptsiteinterruptpollquerycontinue"></a>IActiveScriptSiteInterruptPoll::QueryContinue
使宿主可以指定应终止脚本。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT QueryContinue();  
```  
  
#### <a name="parameters"></a>参数  
 此方法需要任何参数。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|调用成功，且主机允许脚本继续运行。|  
|`S_FALSE`|成功的调用和脚本终止的主机请求。|  
  
## <a name="remarks"></a>备注  
 除非承载的脚本应终止的返回值`QueryContinue`方法是`S_OK`。 返回值为`S_FALSE`指示主机显式请求脚本终止。  
  
 可以使用多线程的主机`IActiveScript::InterruptScriptThread`方法终止脚本。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptSiteInterruptPoll 接口](../../winscript/reference/iactivescriptsiteinterruptpoll-interface.md)   
 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)