---
title: IDebugErrorBreakpoint2::GetBreakpointResolution |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugErrorBreakpoint2::GetBreakpointResolution
helpviewer_keywords:
- IDebugErrorBreakpoint2::GetBreakpointResolution
ms.assetid: 1c2324ed-2a11-4e63-8f3a-f420c7a4018b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6d8a97b3807b76b99544dffdc1884d0cb0de7749
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53893166"
---
# <a name="idebugerrorbreakpoint2getbreakpointresolution"></a>IDebugErrorBreakpoint2::GetBreakpointResolution
获取描述错误断点错误解决方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetBreakpointResolution(   
   IDebugErrorBreakpointResolution2** ppErrorResolution  
);  
```  
  
```csharp  
int GetBreakpointResolution(   
   out IDebugErrorBreakpointResolution2 ppErrorResolution  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppErrorResolution`  
 [out]返回[IDebugErrorBreakpointResolution2](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2.md)描述错误的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)   
 [IDebugErrorBreakpointResolution2](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2.md)