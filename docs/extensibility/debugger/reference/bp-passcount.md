---
title: "BP_PASSCOUNT |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_PASSCOUNT
helpviewer_keywords: BP_PASSCOUNT structure
ms.assetid: 791ac175-b897-4c70-873e-240da7e0ac89
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 62c523ee3d65a7149f8e25304e0b719470242685
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="bppasscount"></a>BP_PASSCOUNT
描述对其触发条件断点的计数和条件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _BP_PASSCOUNT {   
   DWORD              dwPassCount;  
   BP_PASSCOUNT_STYLE stylePassCount;  
} BP_PASSCOUNT;  
```  
  
```csharp  
public struct BP_PASSCOUNT {   
   public uint dwPassCount;  
   public uint stylePassCount;  
};  
```  
  
## <a name="members"></a>成员  
 `dwPassCount`  
 若要触发它之前其需要通过跳过该断点的次数。  
  
 `stylePassCount`  
 取值范围为[BP_PASSCOUNT_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md)指定断点的样式的枚举传递计数。  
  
## <a name="remarks"></a>备注  
 此结构是的成员[BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)结构。  
  
 此结构还传递作为参数传递给[SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)和[SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md)方法。  
  
## <a name="requirements"></a>惠?  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugboundbreakpoint2-setpasscount.md)   
 [SetPassCount](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-setpasscount.md)   
 [BP_PASSCOUNT_STYLE](../../../extensibility/debugger/reference/bp-passcount-style.md)