---
title: IDebugProgramNodeAttach2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramNodeAttach2
helpviewer_keywords:
- IDebugProgramNodeAttach2 interface
ms.assetid: 46b37ac9-a026-4ad3-997b-f19e2f8deb73
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a83f5635dfacb638a2e76054dc5ed4e887e2a3cb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31120684"
---
# <a name="idebugprogramnodeattach2"></a>IDebugProgramNodeAttach2
允许接收通知的尝试将附加到关联的程序的程序节点。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugProgramNodeAttach2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 实现同一类上实现此接口[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)接口为了接收通知的附加操作，并提供机会取消附加操作。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 通过调用来获取此接口`QueryInterface`中的方法[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)对象。 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)前，必须调用方法[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)方法，以便为程序节点有机会停止附加过程。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 此接口实现以下方法：  
  
|方法|描述|  
|------------|-----------------|  
|[OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)|将附加到关联的程序或将推迟到 attach 进程[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)方法。|  
  
## <a name="remarks"></a>备注  
 此接口是不推荐使用的首选的替代[Attach_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)方法。 所有的调试引擎都始终加载有`CoCreateInstance`函数中，即，它们实例化被调试的程序的地址空间外。  
  
 如果以前的实现`IDebugProgramNode2::Attach_V7`只需设置方法`GUID`的被调试的程序，然后仅[OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)需要实现方法。  
  
 如果以前的实现`IDebugProgramNode2::Attach_V7`方法使用回调接口提供，则该功能需要移动到的实现[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)方法和`IDebugProgramNodeAttach2`接口不需要实现。  
  
## <a name="requirements"></a>要求  
 标头： Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [Attach_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)