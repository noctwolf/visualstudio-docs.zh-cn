---
title: IDebugCanStopEvent2::CanStop |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCanStopEvent2::CanStop
helpviewer_keywords:
- IDebugCanStopEvent2::CanStop
ms.assetid: 7d61adbe-6b3d-41f3-86a1-45d9cc01a7f8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a3e2507ba86e00434c12a67ba70cad51fa5850ce
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idebugcanstopevent2canstop"></a>IDebugCanStopEvent2::CanStop
通知的调试引擎 (DE) 以停止在当前的代码位置，或只需继续执行。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CanStop (   
   BOOL fCanStop  
);  
```  
  
```csharp  
int CanStop (   
   int fCanStop  
);  
```  
  
#### <a name="parameters"></a>参数  
 `fCanStop`  
 [in]非零 (`TRUE`) 如果 DE 应停止在当前的代码位置; 否则为零 (`FALSE`)。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 此事件的接收方通常调用[GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)方法以确定 DE 想要停止的原因，然后调用`IDebugCanStopEvent2::CanStop`与适当的响应的方法。  
  
 如果 DE 停止，它将发送事件描述停止的原因。 通常有两个事件发送，由用户或信号中断[IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)接口，并且表示断点事件[IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)接口。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)   
 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)