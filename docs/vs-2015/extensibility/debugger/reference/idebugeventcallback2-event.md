---
title: IDebugEventCallback2::Event |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugEventCallback2::Event
helpviewer_keywords:
- IDebugEventCallback2::Event
ms.assetid: e5a3345b-d460-4e40-8f5b-3111c56a2ed9
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cddaa351ed406299d5ddf1247025f5d442fb3d3b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47472241"
---
# <a name="idebugeventcallback2event"></a>IDebugEventCallback2::Event
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugEventCallback2::Event](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugeventcallback2-event)。  
  
发送通知的调试事件。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Event(   
   IDebugEngine2*  pEngine,  
   IDebugProcess2* pProcess,  
   IDebugProgram2* pProgram,  
   IDebugThread2*  pThread,  
   IDebugEvent2*   pEvent,  
   REFIID          riidEvent,  
   DWORD           dwAttrib  
);  
```  
  
```csharp  
int Event(   
   IDebugEngine2  pEngine,  
   IDebugProcess2 pProcess,  
   IDebugProgram2 pProgram,  
   IDebugThread2  pThread,  
   IDebugEvent2   pEvent,  
   ref Guid       riidEvent,  
   uint           dwAttrib  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pEngine`  
 [in][IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)对象，表示发送此事件的调试引擎 (DE)。 DE 需要填写此参数。  
  
 `pProcess`  
 [in][IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)表示的过程时发生该事件的对象。 此参数由会话调试管理器 (SDM) 填充。 DE 始终将传递此参数的 null 值。  
  
 `pProgram`  
 [in][IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)表示的程序发生此事件的对象。 对于大多数事件，此参数不是 null 值。  
  
 `pThread`  
 [in][IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)对象，表示发生此事件的线程。 停止事件，此参数不能为 null 值，从此参数获取的堆栈帧。  
  
 `pEvent`  
 [in][IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)表示调试事件的对象。  
  
 `riidEvent`  
 [in]GUID，用于标识哪个事件接口，以获取从`pEvent`参数。  
  
 `dwAttrib`  
 [in]中的标志的组合[EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md)枚举。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 调用此方法时`dwAttrib`参数必须与从返回的值匹配[GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)方法，如对事件对象调用中传递`pEvent`参数。  
  
 以异步方式，而不考虑事件本身是否是异步发布所有调试事件。 DE 调用此方法时，返回值不指示是否在事件处理，仅是否收到事件。 事实上，在大多数情况下，该事件尚未处理此方法返回时。  
  
## <a name="see-also"></a>请参阅  
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [EVENTATTRIBUTES](../../../extensibility/debugger/reference/eventattributes.md)

