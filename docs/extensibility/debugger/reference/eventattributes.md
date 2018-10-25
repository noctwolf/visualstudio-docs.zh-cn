---
title: EVENTATTRIBUTES |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- EVENTATTRIBUTES
helpviewer_keywords:
- EVENTATTRIBUTES enumeration
ms.assetid: 04db10f7-df31-4464-98e8-b3777428179e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7df726716e464ccc4bf8382b38fbb0b8d277df86
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49893815"
---
# <a name="eventattributes"></a>EVENTATTRIBUTES
指定的事件属性。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
typedef DWORD EVENTATTRIBUTES;  
```  
  
```csharp  
public enum enum_EVENTATTRIBUTES {   
   EVENT_ASYNCHRONOUS          = 0x0000,  
   EVENT_SYNCHRONOUS           = 0x0001,  
   EVENT_STOPPING              = 0x0002,  
   EVENT_ASYNC_STOP            = 0x0002,  
   EVENT_SYNC_STOP             = 0x0003,  
   EVENT_IMMEDIATE             = 0x0004,  
   EVENT_EXPRESSION_EVALUATION = 0x0008  
};  
```  
  
## <a name="members"></a>成员  
 EVENT_ASYNCHRONOUS  
 指示事件是异步的需要该事件没有收到回复。  
  
 EVENT_SYNCHRONOUS  
 指示事件是同步的通过答复[ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)。  
  
 EVENT_STOPPING  
 指示这是一个停止事件。 必须使用组合`EVENT_ASYNCHRONOUS`或`EVENT_SYNCHRONOUS`。  
  
 EVENT_ASYNC_STOP  
 表示异步停止事件。 当前没有此类事件。 此标志只是一个占位符。  
  
 EVENT_SYNC_STOP  
 指示同步停止事件 (的组合`EVENT_SYNCHRONOUS`和`EVENT_STOPPING`)。 发送 stopping 事件时，调试引擎 (DE) 使用此值。 通过调用进行答复[Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md)，[步骤](../../../extensibility/debugger/reference/idebugprogram2-step.md)，或[继续](../../../extensibility/debugger/reference/idebugprogram2-continue.md)。  
  
 EVENT_IMMEDIATE  
 指示将立即并以同步方式发送到 IDE 的事件。 此标志结合了等其他标志`EVENT_ASYNCHRONOUS`， `EVENT_SYNCHRONOUS`，或`EVENT_SYNC_STOP`来指示类型的事件，并在已知 （如果有） 的回复机制。  
  
 EVENT_EXPRESSION_EVALUATION  
 该事件为表达式计算的结果。  
  
## <a name="remarks"></a>备注  
 这些值将按传递`dwAttrib`的参数[事件](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)方法。  
  
 可能的按位组合这些值`OR`。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)