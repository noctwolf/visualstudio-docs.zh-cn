---
title: IDebugObject |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject
helpviewer_keywords:
- IDebugObject interface
ms.assetid: 05cd8bf4-c9ee-4b49-b782-2263c33067d6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4cff859d2aa4b3a3c88978e077102e045efe1f3b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31120996"
---
# <a name="idebugobject"></a>IDebugObject
> [!IMPORTANT]
>  在 Visual Studio 2015 中，已弃用这种方式实施表达式计算器。 有关实现 CLR 表达式计算器的信息，请参阅[CLR 表达式计算器](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)和[托管表达式计算器示例](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)。  
  
 此接口表示联编程序创建封装符号和表达式的值的对象。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugObject : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 表达式计算器实现此接口可表示的对象。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 此接口是表达式计算器分析表达式中使用的所有对象的基类。 返回通过调用[绑定](../../../extensibility/debugger/reference/idebugbinder-bind.md)方法。 [QueryInterface](/cpp/atl/queryinterface)此接口中获取的专用化程度的接口。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugObject`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetSize](../../../extensibility/debugger/reference/idebugobject-getsize.md)|获取对象的大小。|  
|[GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)|作为一系列连续字节中获取对象的值。|  
|[SetValue](../../../extensibility/debugger/reference/idebugobject-setvalue.md)|设置对象的值从一系列连续的字节。|  
|[SetReferenceValue](../../../extensibility/debugger/reference/idebugobject-setreferencevalue.md)|设置此对象的引用值。|  
|[GetMemoryContext](../../../extensibility/debugger/reference/idebugobject-getmemorycontext.md)|获取表示对象的值的地址的内存上下文。|  
|[GetManagedDebugObject](../../../extensibility/debugger/reference/idebugobject-getmanageddebugobject.md)|创建的调试引擎的地址空间中的托管对象的副本。|  
|[IsNullReference](../../../extensibility/debugger/reference/idebugobject-isnullreference.md)|测试此对象是否为空引用。|  
|[IsEqual](../../../extensibility/debugger/reference/idebugobject-isequal.md)|将此对象进行比较。|  
|[IsReadOnly](../../../extensibility/debugger/reference/idebugobject-isreadonly.md)|确定此对象是否为只读的。|  
|[IsProxy](../../../extensibility/debugger/reference/idebugobject-isproxy.md)|确定对象是否为透明的代理。|  
  
## <a name="remarks"></a>备注  
 表达式计算器使用的基类为此接口来表示分析树中的对象。  
  
## <a name="requirements"></a>要求  
 标头： ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [表达式评估接口](../../../extensibility/debugger/reference/expression-evaluation-interfaces.md)   
 [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md)   
 [绑定](../../../extensibility/debugger/reference/idebugbinder-bind.md)