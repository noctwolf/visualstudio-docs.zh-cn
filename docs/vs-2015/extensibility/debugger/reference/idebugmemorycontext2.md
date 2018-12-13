---
title: IDebugMemoryContext2 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugMemoryContext2
helpviewer_keywords:
- IDebugMemoryContext2 interface
ms.assetid: 3a544c8b-11dc-46bb-8549-261e4ac5bbc4
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d19bad3f5ec4459c6aacf7b6456be9afb956043a
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51741181"
---
# <a name="idebugmemorycontext2"></a>IDebugMemoryContext2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此接口表示运行正在调试的程序的计算机的地址空间中的位置。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugMemoryContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 调试引擎 (DE) 实现此接口来表示内存中的地址。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 调用[GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)或[GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md)返回此接口。 此外，调用[外](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md)并[Subtract](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md)应用适当的算术运算后返回的此接口的新副本。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugMemoryContext2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetName](../../../extensibility/debugger/reference/idebugmemorycontext2-getname.md)|获取此上下文中的用户可显示名称。|  
|[GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)|获取描述此上下文的信息。|  
|[添加](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md)|将指定的值添加到当前上下文的地址以创建新的上下文。|  
|[相减](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md)|减去指定的值从当前上下文的地址以创建新的上下文。|  
|[Compare](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)|比较两个上下文的方式指示比较标志。|  
  
## <a name="remarks"></a>备注  
 Visual Studio**内存**窗口中调用[GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)若要获取`IDebugMemoryContext2`包含计算的表达式使用的内存地址的接口。 然后将此上下文传递给[ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)并[WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)来指定要读取或写入的地址。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md)   
 [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)   
 [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)

