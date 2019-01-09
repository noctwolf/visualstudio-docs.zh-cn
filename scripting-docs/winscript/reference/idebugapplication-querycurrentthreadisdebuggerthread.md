---
title: IDebugApplication::QueryCurrentThreadIsDebuggerThread |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.QueryCurrentThreadIsDebuggerThread
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::QueryCurrentThreadIsDebuggerThread
ms.assetid: e22ad8a4-a8be-423d-80f2-28256a7448ed
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 12febbc2cc7aeaee5113c38837e073bba10d7a17
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087628"
---
# <a name="idebugapplicationquerycurrentthreadisdebuggerthread"></a>IDebugApplication::QueryCurrentThreadIsDebuggerThread
确定当前正在运行的线程是调试器线程。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT QueryCurrentThreadIsDebuggerThread();  
```  
  
#### <a name="parameters"></a>参数  
 此方法需要任何参数。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|该方法成功，并且当前正在运行的线程是调试器线程。|  
|`S_FALSE`|当前正在运行的线程不是调试器线程。|  
  
## <a name="remarks"></a>备注  
 此方法确定当前正在运行的线程是调试器线程。  
  
## <a name="see-also"></a>请参阅  
 [IDebugApplication 接口](../../winscript/reference/idebugapplication-interface.md)