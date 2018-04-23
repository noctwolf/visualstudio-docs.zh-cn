---
title: 进程 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], processes
ms.assetid: a6a1efdc-b243-40c8-a778-6f69f6b018be
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 75230740e84bb6660629b38e84df56fa8e5c1856
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="processes"></a>进程
在调试器体系结构，方面**过程**:  
  
-   是一组程序的容器。 它是非常类似于 Windows 进程，这是一组的线程的容器。  
  
-   可以将自己标识的名称、 标识符或物理标识符。  
  
-   可以枚举运行的所有程序 （和其线程）。  
  
-   可以描述本身、，在运行的端口和包含它的计算机。  
  
-   可以创建一个或多个程序终止的任何程序创建，或导致程序停止。  
  
-   由[IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)接口，启动进程时创建的。 由任一会话调试管理器 (SDM) 启动进程或[LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)。  
  
 调试包可以调试引擎 (DE) 通过附加到进程调用[附加](../../extensibility/debugger/reference/idebugprocess2-attach.md)。 这意味着，DE 将附加到所有可能的程序在它可以处理的过程中运行。 例如，如果公共语言运行时 DE 附加到进程，附加仅到正在运行托管的代码的程序。  
  
## <a name="see-also"></a>另请参阅  
 [程序](../../extensibility/debugger/programs.md)   
 [线程](../../extensibility/debugger/threads.md)   
 [调试器概念](../../extensibility/debugger/debugger-concepts.md)   
 [调试包](../../extensibility/debugger/debug-package.md)   
 [调试引擎](../../extensibility/debugger/debug-engine.md)   
 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [附加](../../extensibility/debugger/reference/idebugprocess2-attach.md)