---
title: IDebugBoundBreakpoint2::GetPendingBreakpoint |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugBoundBreakpoint2::GetPendingBreakpoint
helpviewer_keywords:
- IDebugBoundBreakpoint2::GetPendingBreakpoint method
- GetPendingBreakpoint method
ms.assetid: 22f94f81-f8d9-46de-96e9-fae6f3c24903
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 899afbc801baee88dd941763b559845b90be8500
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109504"
---
# <a name="idebugboundbreakpoint2getpendingbreakpoint"></a>IDebugBoundBreakpoint2::GetPendingBreakpoint
获取从中创建指定的绑定的断点挂起断点。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetPendingBreakpoint(   
   IDebugPendingBreakpoint2** ppPendingBreakpoint  
);  
```  
  
```csharp  
int GetPendingBreakpoint(   
   out IDebugPendingBreakpoint2 ppPendingBreakpoint  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppPendingBreakpoint`  
 [out]返回[IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)对象，表示用于创建此挂起断点绑定断点。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 挂起断点可以看作将断点绑定到可以应用于一个或多个程序的代码所需的所有必要的信息的集合。  
  
## <a name="example"></a>示例  
 下面的示例演示如何实现此方法对于简单`CBoundBreakpoint`公开的对象[IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)接口。  
  
```  
HRESULT CBoundBreakpoint::GetPendingBreakpoint(  
    IDebugPendingBreakpoint2** ppPendingBreakpoint)  
{    
   HRESULT hr;    
  
   // Check for valid IDebugPendingBreakpoint2 interface pointer.    
   if (ppPendingBreakpoint)    
   {    
      // Be sure that the bound breakpoint has not been deleted. If  
      // deleted, then return hr = E_BP_DELETED.    
      if (m_state != BPS_DELETED)    
      {    
         // Query for the IDebugPendingBreakpoint2 interface.    
         hr = m_pPendingBP->QueryInterface(IID_IDebugPendingBreakpoint2,  
                                           (void**)ppPendingBreakpoint);    
      }    
      else    
      {    
         hr = E_BP_DELETED;    
      }    
   }    
   else    
   {    
      hr = E_INVALIDARG;    
   }    
  
   return hr;    
}    
```  
  
## <a name="see-also"></a>另请参阅  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)