---
title: 控件编程 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], control of execution
ms.assetid: 6be80904-e66c-4cae-8891-1113b799fb01
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8c227f38c926cb6d764ddf47541b8bd744eb6f7c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31102085"
---
# <a name="program-control"></a>程序控件
Visual Studio 中调试，所有以下单步执行和继续例程在级别上发生程序：  
  
-   设置下一条语句，也就是说，将你的计算机设置为在特定帧环境中执行的下一步指令  
  
-   执行时，即，继续退出单步执行模式  
  
-   单步执行到下一步指令  
  
-   继续执行当前的单步执行模式  
  
-   挂起包含的程序的线程  
  
-   恢复包含的程序的线程  
  
> [!NOTE]
>  在线程级别上执行时查看调用堆栈。 若要查看线程的调用堆栈时枚举的帧的信息，则必须实现的所有方法[IEnumDebugFrameInfo2](../../extensibility/debugger/reference/ienumdebugframeinfo2.md)接口。  
  
## <a name="methods-of-program-control"></a>程序控制的方法  
 下表显示的方法[IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) ，必须为最小功能的调试引擎 (DE) 和执行控制实现。  
  
|方法|描述|  
|------------|-----------------|  
|[IDebugProgram2::Execute](../../extensibility/debugger/reference/idebugprogram2-execute.md)|将继续运行将程序从此停止状态所包含的所有线程。 所需执行控制的。|  
|[IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md)|将继续运行将程序从此停止状态所包含的所有线程。 所需执行控制的。|  
|[IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md)|在给定的线程上执行一个步骤。 将继续运行程序所包含的所有其他线程。 所需执行控制的。|  
  
 对于多线程程序中，你还必须实现[IDebugProgram2::EnumThreads](../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)方法和的所有方法[IEnumDebugThreads2](../../extensibility/debugger/reference/ienumdebugthreads2.md)接口。  
  
## <a name="see-also"></a>另请参阅  
 [执行控件和状态计算](../../extensibility/debugger/execution-control-and-state-evaluation.md)