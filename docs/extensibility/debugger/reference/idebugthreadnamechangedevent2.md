---
title: "IDebugThreadNameChangedEvent2 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugThreadNameChangedEvent2
helpviewer_keywords: IDebugThreadNameChangedEvent2
ms.assetid: 34c1652e-f019-48ba-8b26-ace20f8a158c
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 213294333632f274feb62cbbf5b1a380fa1d2d95
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugthreadnamechangedevent2"></a>IDebugThreadNameChangedEvent2
正在调试的程序中的线程名称更改时，此接口是由的调试引擎 (DE) 发送到会话调试管理器 (SDM) 中。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugThreadNameChangedEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 DE 实现此接口到线程的名称已更改的报表。 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)接口必须实现该接口对同一个对象。 SDM 使用[QueryInterface](/cpp/atl/queryinterface)访问`IDebugEvent2`接口。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 DE 创建，并将此事件对象发送到线程的名称已更改的报表。 通过使用发送事件[IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) SDM 时将其附加到正在调试的程序提供的回调函数。  
  
## <a name="requirements"></a>惠?  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)