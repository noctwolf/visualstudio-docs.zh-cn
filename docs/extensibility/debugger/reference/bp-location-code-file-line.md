---
title: BP_LOCATION_CODE_FILE_LINE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_CODE_FILE_LINE
helpviewer_keywords:
- BP_LOCATION_CODE_FILE_LINE structure
ms.assetid: 3ff32032-d412-44d3-91bf-870cc354a09e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 52ad83e4ad79bb305143fd4f648e7e32131f8889
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53847897"
---
# <a name="bplocationcodefileline"></a>BP_LOCATION_CODE_FILE_LINE
包含在代码源文件中的特定行断点的位置的数据。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _BP_LOCATION_CODE_FILE_LINE {   
   BSTR                     bstrContext;  
   IDebugDocumentPosition2* pDocPos;  
} BP_LOCATION_CODE_FILE_LINE;  
```  
  
## <a name="members"></a>成员  
 `bstrContext`  
 该断点的上下文，通常显示调用堆栈上的方法或函数名称。  
  
 `pDocPos`  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)对象，表示该断点的文档位置。  
  
## <a name="remarks"></a>备注  
 此结构是的成员[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)结构作为联合的一部分。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)