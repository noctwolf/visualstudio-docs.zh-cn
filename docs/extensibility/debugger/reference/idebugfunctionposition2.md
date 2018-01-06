---
title: "IDebugFunctionPosition2 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugFunctionPosition2
helpviewer_keywords: IDebugFunctionPosition2 interface
ms.assetid: a835f65b-91b0-48ad-8485-04534c814b1b
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 6494f01a10177cc0e3fa0eb1724f64b7301e06aa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfunctionposition2"></a>IDebugFunctionPosition2
此接口表示源文档中的函数的抽象位置。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugFunctionPosition2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 调试引擎 (DE) 实现此接口来表示源文档中的函数的位置。  
  
## <a name="notes-for-callers"></a>调用方的说明  
 此接口提供的一部分[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)联合 (具体而言， [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)结构)，又是的一部分[BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)结构，用于创建挂起断点。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
 下表显示的方法`IDebugFunctionPosition2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetFunctionName](../../../extensibility/debugger/reference/idebugfunctionposition2-getfunctionname.md)|获取此位置是相对于函数的名称。|  
|[GetOffset](../../../extensibility/debugger/reference/idebugfunctionposition2-getoffset.md)|获取从函数的开头的偏移量。|  
  
## <a name="remarks"></a>备注  
 表示通过此接口的位置是基于文本的具体而言， [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)结构。  
  
## <a name="requirements"></a>惠?  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)   
 [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)