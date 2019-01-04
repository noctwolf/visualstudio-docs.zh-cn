---
title: 终止程序 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- programs, termination events
- debugging [Debugging SDK], terminating a program
ms.assetid: eedda0a3-5e05-44fe-841d-a2f4866ac72d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 28be8f34602a3a175c40d630463686f0ca99c919
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53958847"
---
# <a name="terminating-a-program"></a>终止程序
以下部分介绍了一个线程使用单个程序终止。  
  
## <a name="termination-process"></a>终止进程  
  
1. DE 发送[IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md)使用一个有效[IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md)。  
  
2. DE 发送[IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)使用一个有效[IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)。  
  
   IDE 将进入设计模式。 调试引擎或运行时环境调用[IDebugPortNotify2::RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)从端口删除该程序。  
  
## <a name="see-also"></a>请参阅  
 [调用调试器事件](../../extensibility/debugger/calling-debugger-events.md)