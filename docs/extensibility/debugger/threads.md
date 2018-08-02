---
title: 线程 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], threads
- threading [Debugging SDK]
ms.assetid: 2243d24a-c3d2-41d1-abbb-6db21a2db9ee
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 456ec81c5f39f533bddd58d0a9e4d9d5889f066d
ms.sourcegitcommit: 8d38d5d2f2b75fc1563952c0d6de0fe43af12766
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2018
ms.locfileid: "39276629"
---
# <a name="threads"></a>线程
在调试器体系结构中，*线程*:  
  
-   是计算的基本单位。 线程按顺序执行其上下文中的单一调用堆栈，将从一种代码上下文移到下一步的说明。  
  
-   可以标识本身和在运行的程序。 可以命名、 挂起，但恢复线程。 线程还可以枚举其关联的堆栈帧，并在某些情况下可以移动到另一个堆栈帧。 给定堆栈帧上下文内的，线程可以返回其关联的逻辑线程，如果有的话。 线程具有属性，例如挂起计数，在中显示**线程**在 IDE 的窗口。  
  
-   为由[IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md)接口，通常创建的调试引擎 (DE) 或虚拟机，因此执行程序。  
  
## <a name="see-also"></a>请参阅  
 [程序](../../extensibility/debugger/programs.md)   
 [堆栈帧](../../extensibility/debugger/stack-frames.md)   
 [调试引擎](../../extensibility/debugger/debug-engine.md)   
 [调试器概念](../../extensibility/debugger/debugger-concepts.md)   
 [会话调试管理器](../../extensibility/debugger/session-debug-manager.md)