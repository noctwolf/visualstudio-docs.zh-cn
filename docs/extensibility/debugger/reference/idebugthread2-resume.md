---
title: IDebugThread2::Resume | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugThread2::Resume
helpviewer_keywords:
- IDebugThread2::Resume
ms.assetid: 36aad682-b0b9-40a2-b3fc-f0e61d41cdbc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 807f89eeed4e85e86c1a09a34ae12744bac8e0ae
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54935262"
---
# <a name="idebugthread2resume"></a>IDebugThread2::Resume
继续执行线程。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Resume (   
   DWORD *pdwSuspendCount  
);  
```  
  
```csharp  
int Resume (   
   out uint pdwSuspendCount  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdwSuspendCount`  
 [out]恢复操作完成后返回的挂起计数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 每个调用此方法可将挂起计数直到中哪些时间达到 0，实际恢复执行。 此挂起计数显示在**线程**调试窗口。  
  
 对于每次调用此方法，必须有以前调用[挂起](../../../extensibility/debugger/reference/idebugthread2-suspend.md)方法。 挂起计数确定多少次`IDebugThread2::Suspend`到目前为止已调用方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Suspend](../../../extensibility/debugger/reference/idebugthread2-suspend.md)