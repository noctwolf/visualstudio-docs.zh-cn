---
title: 程序控制 |Microsoft Docs
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
ms.openlocfilehash: a60b766763ca5f68f8c379fbab9372e41c319671
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251093"
---
# <a name="program-control"></a>程序控制
在 Visual Studio 中调试时，所有以下单步执行和继续例程出现在程序级别上：  
  
-   设置下一条语句，即，将您的计算机设置为在特定帧的环境中执行的下一个指令  
  
-   执行时，即继续退出单步执行模式  
  
-   单步执行到下一个指令  
  
-   继续执行当前单步执行模式  
  
-   挂起线程所包含的程序  
  
-   继续执行所包含的程序线程  
  
> [!NOTE]
>  在线程级别上实现查看调用堆栈。 若要枚举帧信息查看线程的调用堆栈时，必须实现的所有方法[IEnumDebugFrameInfo2](../../extensibility/debugger/reference/ienumdebugframeinfo2.md)接口。  
  
## <a name="methods-of-program-control"></a>程序控件的方法  
 下表显示的方法[IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) ，必须实现最小功能调试引擎 (DE) 和执行控制。  
  
|方法|描述|  
|------------|-----------------|  
|[IDebugProgram2::Execute](../../extensibility/debugger/reference/idebugprogram2-execute.md)|将继续运行所包含的程序已停止状态的所有线程。 所需的执行控制。|  
|[IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md)|将继续运行所包含的程序已停止状态的所有线程。 所需的执行控制。|  
|[IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md)|在给定的线程上执行一个步骤。 将继续运行程序所包含的所有其他线程。 所需的执行控制。|  
  
 对于多线程程序，您还必须实现[IDebugProgram2::EnumThreads](../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)方法和的所有方法[IEnumDebugThreads2](../../extensibility/debugger/reference/ienumdebugthreads2.md)接口。  
  
## <a name="see-also"></a>请参阅  
 [执行控件和状态评估](../../extensibility/debugger/execution-control-and-state-evaluation.md)