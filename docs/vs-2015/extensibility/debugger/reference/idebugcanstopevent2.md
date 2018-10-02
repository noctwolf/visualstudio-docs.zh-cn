---
title: IDebugCanStopEvent2 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugCanStopEvent2
helpviewer_keywords:
- IDebugBreakpointRequest2 interface
ms.assetid: 784bd5b1-4a3f-4455-b313-c4c9a82555a5
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e196a9552b1dbfadbbd26e004565369fbf1d9dba
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481560"
---
# <a name="idebugcanstopevent2"></a>IDebugCanStopEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugCanStopEvent2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcanstopevent2)。  
  
使用此接口要求会话调试管理器 (SDM) 是否在当前代码位置停止。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugCanStopEvent2 : IUknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 调试引擎 (DE) 实现此接口以支持单步执行源代码。 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)接口必须实现此接口作为对同一个对象 (使用 SDM [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3)访问`IDebugEvent2`接口)。  
  
 此接口的实现必须进行通信的 SDM 的调用[CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)到调试引擎。 例如，这可以通过一条消息发布到调试引擎的消息处理线程或实现此接口的对象无法保存对调试引擎的引用并回调到调试引擎传递到标志`IDebugCanStopEvent2::CanStop`。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 DE 可以发送此方法每次 DE 需要继续执行，DE 逐句通过代码。 通过使用发送此事件[IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) SDM 它附加到正在调试的程序时所提供的回调函数。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugCanStopEvent2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)|获取此事件的原因。|  
|[CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)|指定是否正在调试的程序应在此事件 （和发送描述停止的原因的事件） 的位置停止，或只需继续执行。|  
|[GetDocumentContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getdocumentcontext.md)|获取用于描述此事件的位置的文档上下文。|  
|[GetCodeContext](../../../extensibility/debugger/reference/idebugcanstopevent2-getcodecontext.md)|获取用于描述此事件的位置的代码上下文。|  
  
## <a name="remarks"></a>备注  
 如果用户单步执行函数，DE 查找任何调试信息或调试信息存在但 DE 不知道如果可以对该位置显示的源代码，DE 发送此接口。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [IDebugStepCompleteEvent2](../../../extensibility/debugger/reference/idebugstepcompleteevent2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)

