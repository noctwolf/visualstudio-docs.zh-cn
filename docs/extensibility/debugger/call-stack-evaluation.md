---
title: 调用堆栈评估 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], call stack evaluation
- call stacks, evaluation
ms.assetid: 373d6b49-0459-4cce-816e-05745a44fe49
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bcfc2f2afa622534772390df59597f6972463de8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31101298"
---
# <a name="call-stack-evaluation"></a>调用堆栈评估
若要在中断模式下查看调用堆栈的堆栈帧，则必须实现[EnumFrameInfo](../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)方法。  
  
## <a name="methods-for-evaluation"></a>用于评估方法  
 对于简单的调试引擎 (DE)，可能只有一个堆栈帧。 若要检查在中断模式期间的堆栈帧，则必须实现以下的方法[IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md)。  
  
|方法|描述|  
|------------|-----------------|  
|[GetCodeContext](../../extensibility/debugger/reference/idebugstackframe2-getcodecontext.md)|获取一个堆栈帧的代码上下文。 代码上下文表示当前指令指针的堆栈帧中。|  
|[GetDocumentContext](../../extensibility/debugger/reference/idebugstackframe2-getdocumentcontext.md)|获取一个堆栈帧的文档上下文。 文档上下文表示当前堆栈帧的源代码中的位置。 所需的程序中停止时查看的源代码。|  
  
 这些方法需要多个上下文相关接口和方法的实现。 因此，必须实现[GetDocumentContext](../../extensibility/debugger/reference/idebugcodecontext2-getdocumentcontext.md)方法以及的以下方法[IDebugDocumentContext2](../../extensibility/debugger/reference/idebugdocumentcontext2.md)。  
  
|方法|描述|  
|------------|-----------------|  
|[GetStatementRange](../../extensibility/debugger/reference/idebugdocumentcontext2-getstatementrange.md)|获取文件语句范围的文档上下文。|  
  
 若要枚举代码上下文，则必须实现的所有方法[IEnumDebugCodeContexts2](../../extensibility/debugger/reference/ienumdebugcodecontexts2.md)。  
  
## <a name="see-also"></a>另请参阅  
 [执行控件和状态计算](../../extensibility/debugger/execution-control-and-state-evaluation.md)