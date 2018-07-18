---
title: IDebugExpressionContext2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugExpressionContext2
helpviewer_keywords:
- IDebugExpressionContext2 interface
ms.assetid: 577fdaae-4b2d-4112-9839-ab899535fa6f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4da916f67611f594b14a41cbb2838f4565eb7fe3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31115432"
---
# <a name="idebugexpressioncontext2"></a>IDebugExpressionContext2
此接口表示为表达式计算上下文  
  
## <a name="syntax"></a>语法  
  
```  
IDebugExpressionContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 调试引擎 (DE) 实现此接口来表示表达式可以计算的上下文。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用[GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)返回此接口。 仅当已暂停正在调试的程序，堆栈帧可用时，此接口是可访问。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugExpressionContext2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetName](../../../extensibility/debugger/reference/idebugexpressioncontext2-getname.md)|检索评估上下文的名称。|  
|[ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)|分析评估一个基于文本的表达式。|  
  
## <a name="remarks"></a>备注  
 评估上下文可以看作执行表达式计算的作用域。  
  
 当程序已暂停时，会话调试管理器 (SDM) 堆栈帧将从获取通过调用 DE [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)。 然后调用 SDM [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)获取`IDebugExpressionContext2`接口。 这一切后跟调用[ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)创建[IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)接口，表示已分析的准备要进行求值表达式。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetExpressionContext](../../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)   
 [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)