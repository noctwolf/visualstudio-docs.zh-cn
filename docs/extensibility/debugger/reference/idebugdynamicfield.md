---
title: IDebugDynamicField |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDynamicField
helpviewer_keywords:
- IDebugDynamicField interface
ms.assetid: caffbd95-7596-4714-84b1-b964e89a78bb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 378107570f50369ae46c609b0fe2e5099d5adab6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31105156"
---
# <a name="idebugdynamicfield"></a>IDebugDynamicField
此接口表示一个变量的类型。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugDynamicField : IDebugField  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 符号提供程序作为可以在运行时确定的任何类型的基类实现此接口。 这是仅用于托管代码。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 此接口表示专用化程度的接口可以派生自的基类。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 此接口不提供任何方法而非继承自`IDebugField`。  
  
## <a name="requirements"></a>要求  
 标头： sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [符号提供程序接口](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)