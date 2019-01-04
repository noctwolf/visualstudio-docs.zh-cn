---
title: IDebugFunctionPosition2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugFunctionPosition2
helpviewer_keywords:
- IDebugFunctionPosition2 interface
ms.assetid: a835f65b-91b0-48ad-8485-04534c814b1b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 61fd298b1bbbf28f7a7fe514a01dc5707c35e04b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53840929"
---
# <a name="idebugfunctionposition2"></a>IDebugFunctionPosition2
此接口表示源文档中的函数的抽象位置。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugFunctionPosition2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 调试引擎 (DE) 实现此接口来表示源文档内的某个函数的位置。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 此接口提供的一部分[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) union (具体而言， [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)结构)，又是一部分[BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)结构，用于创建挂起断点。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugFunctionPosition2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetFunctionName](../../../extensibility/debugger/reference/idebugfunctionposition2-getfunctionname.md)|获取此位置是相对于函数的名称。|  
|[GetOffset](../../../extensibility/debugger/reference/idebugfunctionposition2-getoffset.md)|获取从该函数的开头的偏移量。|  
  
## <a name="remarks"></a>备注  
 表示通过此接口的位置是基于文本的具体而言， [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)结构。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)