---
title: IDebugProgramEx2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramEx2
helpviewer_keywords:
- IDebugProgramEx2 interface
ms.assetid: 663359ed-635a-4539-addb-0cc52f19d1bd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d8e26a21e00ff9f0fff664130171a302667ee414
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31120957"
---
# <a name="idebugprogramex2"></a>IDebugProgramEx2
此接口允许调试管理器 (SDM) 附加到某个程序，并获取与程序相关联的程序节点的会话。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugProgramEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 自定义端口供应商提供对同一个对象作为实现此接口[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)接口，以便让附加到某个程序，同时允许端口供应商联系，以跟踪所有会话在附加到时 SDM程序。 自定义端口供应商可以实现此接口，如果它选择。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 SDM 调用[QueryInterface](/cpp/atl/queryinterface)上`IDebugProgram2`接口，以获得此接口可跟踪已附加到程序的会话。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugProgramEx2`。  
  
|方法|描述|  
|------------|-----------------|  
|[附加](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)|将程序附加到会话。|  
|[GetProgramNode](../../../extensibility/debugger/reference/idebugprogramex2-getprogramnode.md)|获取与程序关联的程序节点。|  
  
## <a name="remarks"></a>备注  
 此接口是私有 SDM 与程序之间。  
  
## <a name="requirements"></a>要求  
 标头： Portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)