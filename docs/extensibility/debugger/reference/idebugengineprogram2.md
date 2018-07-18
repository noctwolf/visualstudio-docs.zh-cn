---
title: IDebugEngineProgram2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngineProgram2
helpviewer_keywords:
- IDebugEngineProgram2 interface
ms.assetid: 151003a9-2e4d-4acf-9f4d-365dfa6b9596
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ff075605371d39f9d3ff04df01c7022c52e809ef
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31112218"
---
# <a name="idebugengineprogram2"></a>IDebugEngineProgram2
此接口提供多线程调试支持。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugEngineProgram2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 调试引擎实现此接口可支持多个线程同时进行调试。 实现的相同对象上实现此接口[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)接口。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 使用[QueryInterface](/cpp/atl/queryinterface)获取此接口从`IDebugProgram2`接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugEngineProgram2`。  
  
|方法|描述|  
|------------|-----------------|  
|[Stop](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)|停止所有线程在此程序中运行。|  
|[WatchForThreadStep](../../../extensibility/debugger/reference/idebugengineprogram2-watchforthreadstep.md)|用于执行 （或停止执行监视） 监视给定线程上发生。|  
|[WatchForExpressionEvaluationOnThread](../../../extensibility/debugger/reference/idebugengineprogram2-watchforexpressionevaluationonthread.md)|允许 （或不允许） 表达式计算上才会出现的给定线程，即使程序已停止。|  
  
## <a name="remarks"></a>备注  
 Visual Studio 会调用此接口以响应[IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)事件并设置该程序的"监视的线程步骤"和"监视的表达式评估上线程"状态。 [停止](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)每当调用的程序即将停止; 此方法为提供程序终止所有线程的机会。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)