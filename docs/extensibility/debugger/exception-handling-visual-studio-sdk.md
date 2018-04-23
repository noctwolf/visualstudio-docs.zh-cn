---
title: 异常处理 (Visual Studio SDK) |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], exception handling
ms.assetid: 7279dc16-db14-482c-86b8-7b3da5a581d2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 646479184061b093d5d84f81827a4106bd3cda47
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="exception-handling-visual-studio-sdk"></a>异常处理 (Visual Studio SDK)
下面描述所发生异常时的过程。  
  
## <a name="exception-handling-process"></a>异常处理过程  
  
1.  如果首先引发异常，但它由正在调试的程序中的异常处理程序之前，将发送的调试引擎 (DE) [IDebugExceptionEvent2](../../extensibility/debugger/reference/idebugexceptionevent2.md)到为停止事件会话调试 manager (SDM)。 `IDebugExceptionEvent2`要是异常 （在调试包中的异常对话框中指定） 的设置指定用户想要停止上首次异常通知的发送。  
  
2.  SDM 调用[IDebugExceptionEvent2::GetException](../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)获取异常的属性。  
  
3.  调试包调用[IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)以确定什么的选项，以向用户显示。  
  
4.  调试包要求用户如何通过打开首次异常对话框中处理异常。  
  
5.  如果用户选择继续，SDM 调用[IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)。  
  
    -   如果该方法返回，则为 S_OK，则调用[IDebugExceptionEvent2::PassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-passtodebuggee.md)。  
  
         -或-  
  
         如果该方法返回 S_FALSE，该程序正在调试有第二个机会处理异常。  
  
6.  如果正在调试的程序没有处理程序的第二个机会异常，将发送 DE`IDebugExceptionEvent2`到作为 SDM **EVENT_SYNC_STOP**。  
  
7.  调试包要求用户如何通过打开首次异常对话框中处理异常。  
  
8.  调试包调用[IDebugExceptionEvent2::CanPassToDebuggee](../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)以确定什么的选项，以向用户显示。  
  
9. 调试包要求用户如何通过打开第二个机会异常对话框中处理异常。  
  
10. 如果该方法返回，则为 S_OK，则调用`IDebugExceptionEvent2::PassToDebuggee`。  
  
## <a name="see-also"></a>另请参阅  
 [调用调试器事件](../../extensibility/debugger/calling-debugger-events.md)