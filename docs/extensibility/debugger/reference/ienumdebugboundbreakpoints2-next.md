---
title: "IEnumDebugBoundBreakpoints2::Next |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugBoundBreakpoints2::Next
helpviewer_keywords: IEnumDebugBoundBreakpoints2::Next
ms.assetid: cb3a249f-2282-4bdc-b6d8-a4ee4bfb8365
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 13fb11be68bf2801f9a9ca88856a5ae7e2801e70
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugboundbreakpoints2next"></a>IEnumDebugBoundBreakpoints2::Next
枚举中返回下一组元素。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Next(  
   ULONG                    celt,  
   IDebugBoundBreakpoint2** rgelt,  
   ULONG*                   pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint                     celt,  
   IDebugBoundBreakpoint2[] rgelt,  
   ref uint                 pceltFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 [in]要检索的元素数。 此外指定的最大大小`rgelt`数组。  
  
 `rgelt`  
 [在中，out]数组[IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)元素填充的。  
  
 `pceltFetched`  
 [out]返回中实际返回的元素数目`rgelt`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果无法返回请求数目的元素少于; 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugBoundBreakpoints2](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2.md)   
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)