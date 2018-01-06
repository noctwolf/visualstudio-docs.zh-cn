---
title: "BP_LOCATION_CODE_CONTEXT |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_LOCATION_CODE_CONTEXT
helpviewer_keywords: BP_LOCATION_CODE_CONTEXT structure
ms.assetid: 37412896-021a-4f73-9bb7-4125502c2e18
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: afe1d63a5496f44e9d55112f0fedf5f4c1822aa0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="bplocationcodecontext"></a>BP_LOCATION_CODE_CONTEXT
描述直接绑定到被调试的程序中的地址的断点的位置。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _BP_LOCATION_CODE_CONTEXT {   
   IDebugCodeContext2* pCodeContext;  
} BP_LOCATION_CODE_CONTEXT;  
```  
  
## <a name="members"></a>成员  
 pCodeContext  
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)对象，用于标识代码中的断点的位置。  
  
## <a name="remarks"></a>备注  
 此结构是的成员[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)作为联合的一部分的结构。  
  
## <a name="requirements"></a>惠?  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)