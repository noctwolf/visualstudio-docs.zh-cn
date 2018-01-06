---
title: "IDebugDynamicField |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugDynamicField
helpviewer_keywords: IDebugDynamicField interface
ms.assetid: caffbd95-7596-4714-84b1-b964e89a78bb
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d1fdd5e0eeb7aeb88b999e72dac875a41c0e0b03
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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
  
## <a name="requirements"></a>惠?  
 标头： sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [符号提供程序接口](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)