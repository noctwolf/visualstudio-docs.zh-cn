---
title: BP_LOCATION_CODE_ADDRESS |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_CODE_ADDRESS
helpviewer_keywords:
- BP_LOCATION_CODE_ADDRESS structure
ms.assetid: 83c9da8b-19d9-4be5-b225-854543654901
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a6d0972b4e326cabd00341db685a0b73c8c104c7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31099117"
---
# <a name="bplocationcodeaddress"></a>BP_LOCATION_CODE_ADDRESS
描述在代码中的一个地址断点的位置。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _BP_LOCATION_CODE_ADDRESS {   
   BSTR bstrContext;  
   BSTR bstrModuleUrl;  
   BSTR bstrFunction;  
   BSTR bstrAddress;  
} BP_LOCATION_CODE_ADDRESS;  
```  
  
## <a name="members"></a>成员  
 `bstrContext`  
 断点的上下文，通常一个方法或函数的名称，作为调用堆栈上看到。  
  
 `bstrModuleUrl`  
 包含断点的模块的 URL。  
  
 `bstrFunction`  
 包含断点的函数的名称。  
  
 `bstrAddress`  
 断点，该表达式计算器才能将其绑定到的分析的地址[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)对象。  
  
## <a name="remarks"></a>备注  
 此结构是的成员[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)作为联合的一部分的结构。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)