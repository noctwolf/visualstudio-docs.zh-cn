---
title: 启动后发送启动事件 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], startup events
ms.assetid: 306ea0b4-6d9e-4871-8d8d-a4032d422940
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 64a2423e3e6900d992ba1a2fafe13f72ab329520
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49927068"
---
# <a name="send-startup-events-after-a-launch"></a>启动后发送启动事件
一旦调试引擎 (DE) 附加到该程序时，会将一系列的启动事件发送到调试会话。  
  
 发送到调试会话的启动事件包括：  
  
- 引擎创建事件。  
  
- 程序创建事件。  
  
- 线程创建和模块加载事件。  
  
- 加载完成事件，发送的代码时加载并准备好运行，但之前执行任何代码。 
  
  > [!NOTE]
  >  当此事件继续执行时，全局变量进行初始化并启动例程运行。  
  
- 可能的其他线程的创建和模块加载事件。  
  
- 入口点事件，表示程序已到达其主入口点，如**Main**或`WinMain`。 如果 DE 将附加到已在运行程序，通常不是发送此事件。  
  
  以编程方式，DE 首先发送会话调试管理器 (SDM) [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md)接口，它表示引擎创建事件后, 跟[IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md)它表示程序创建事件。  
  
  这些事件通常跟一个或多个[IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md)线程创建事件并[IDebugModuleLoadEvent2](../../extensibility/debugger/reference/idebugmoduleloadevent2.md)模块加载事件。  
  
  当该代码加载并准备好运行，但执行任何代码之前，DE 发送 SDM [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md)负载完成事件。 最后，如果程序未运行，DE 发送[IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md)入口点事件，信号程序已达到其主入口点并准备以进行调试。  
  
## <a name="see-also"></a>请参阅  
 [控制执行](../../extensibility/debugger/control-of-execution.md)   
 [调试任务](../../extensibility/debugger/debugging-tasks.md)