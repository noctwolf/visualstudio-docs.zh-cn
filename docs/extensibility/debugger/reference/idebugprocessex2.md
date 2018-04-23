---
title: IDebugProcessEx2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcessEx2
helpviewer_keywords:
- IDebugProcessEx2 interface
ms.assetid: 44e309ba-1d6f-499b-aa7e-9b34858a6d57
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 479206b75325c1b7e6bba0e4cc4e9b53944d73d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprocessex2"></a>IDebugProcessEx2
此接口允许调试管理器 (SDM) 通知它是附加到或与进程分离的进程，会话。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugProcessEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 自定义端口供应商提供对同一个对象作为实现此接口[IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)接口以便为：  
  
-   支持跟踪的会话连接到进程  
  
-   支持自动附加跨多个调试引擎  
  
 自定义端口供应商可以实现此接口，如果它选择。  
  
## <a name="notes-for-callers"></a>调用方的说明  
  
-   SDM 调用[QueryInterface](/cpp/atl/queryinterface)上`IDebugProcess2`接口，以获得此接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugProcessEx2`。  
  
|方法|描述|  
|------------|-----------------|  
|[附加](../../../extensibility/debugger/reference/idebugprocessex2-attach.md)|通知会话现在正在调试的进程的进程。|  
|[分离](../../../extensibility/debugger/reference/idebugprocessex2-detach.md)|通知会话不再调试进程的进程。|  
|[AddImplicitProgramNodes](../../../extensibility/debugger/reference/idebugprocessex2-addimplicitprogramnodes.md)|添加程序节点有关的调试引擎的列表。|  
  
## <a name="remarks"></a>备注  
 此接口是私有 SDM 和进程之间。  
  
## <a name="requirements"></a>要求  
 标头： Portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)