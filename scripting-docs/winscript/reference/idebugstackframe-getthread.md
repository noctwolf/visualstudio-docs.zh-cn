---
title: IDebugStackFrame::GetThread |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugStackFrame.GetThread
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugStackFrame::GetThread
ms.assetid: ece24728-a6b2-4b01-a6f0-0a82b15be39b
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6f6f21c553197a3967619b9aedc25779444185e4
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095740"
---
# <a name="idebugstackframegetthread"></a>IDebugStackFrame::GetThread
返回与此堆栈帧关联的线程。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetThread(  
   IDebugApplicationThread**  ppat  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppat`  
 [out]与此堆栈帧关联的线程。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法返回与此堆栈帧关联的线程。  
  
## <a name="see-also"></a>请参阅  
 [IDebugStackFrame 接口](../../winscript/reference/idebugstackframe-interface.md)