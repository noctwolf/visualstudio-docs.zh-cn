---
title: IDebugMemoryContext2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMemoryContext2
helpviewer_keywords:
- IDebugMemoryContext2 interface
ms.assetid: 3a544c8b-11dc-46bb-8549-261e4ac5bbc4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 26ae199d1fee210559f599cdfe1393aeae5dd169
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31115078"
---
# <a name="idebugmemorycontext2"></a>IDebugMemoryContext2
此接口表示运行被调试的程序的计算机的地址空间中的位置。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugMemoryContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 调试引擎 (DE) 实现此接口来表示内存中的地址。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用[GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)或[GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md)返回此接口。 此外，调用[添加](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md)和[Subtract](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md)应用适当的算术运算后返回的此接口的新副本。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugMemoryContext2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetName](../../../extensibility/debugger/reference/idebugmemorycontext2-getname.md)|获取此上下文的用户可显示名称。|  
|[GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)|获取描述此上下文的信息。|  
|[添加](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md)|将指定的值添加到当前上下文的地址，才能创建新的上下文。|  
|[相减](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md)|从中减去指定的值的当前上下文的地址，才能创建新的上下文。|  
|[Compare](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)|比较方式的两个上下文由比较标志。|  
  
## <a name="remarks"></a>备注  
 Visual Studio 的**内存**窗口调用[GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)获取`IDebugMemoryContext2`包含计算出的表达式用于内存地址的接口。 此上下文随后会传递给[ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)和[WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)以指定要读取或写入的地址。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md)   
 [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)   
 [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)