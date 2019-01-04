---
title: IDebugBeforeSymbolSearchEvent2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugBeforeSymbolSearchEvent2 interface
ms.assetid: 679fd7b1-765a-41a8-a046-63240c09a499
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: aed9c24717866750c3b9139ab2e04b48d5eda960
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53930929"
---
# <a name="idebugbeforesymbolsearchevent2"></a>IDebugBeforeSymbolSearchEvent2
调试引擎 (DE) 期间将发送此接口到会话调试管理器 (SDM) 设置的状态消息栏符号加载。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugBeforeSymbolSearchEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 它必须在符号加载设置状态条消息时，DE 实现此接口。 只能通过使用或属于脚本解释器的调试引擎实现此接口。 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)接口必须实现此接口作为对同一个对象 (使用 SDM **QueryInterface**访问**IDebugEvent2**接口)。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 DE 创建并发送此事件对象，它必须在符号加载设置状态条消息时。 通过使用发送该事件[IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) SDM 它附加到正在调试的程序时所提供的回调函数。  
  
## <a name="methods"></a>方法  
 下表显示的方法`IDebugBeforeSymbolSearchEvent2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetModuleName](../../../extensibility/debugger/reference/idebugbeforesymbolsearchevent2-getmodulename.md)|检索当前正在调试的模块的名称。|  
  
## <a name="requirements"></a>要求  
 标头：Msdbg.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll