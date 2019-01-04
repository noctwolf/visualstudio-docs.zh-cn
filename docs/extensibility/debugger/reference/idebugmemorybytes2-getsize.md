---
title: IDebugMemoryBytes2::GetSize |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugMemoryBytes2::GetSize
helpviewer_keywords:
- IDebugMemoryBytes2::GetSize method
- GetSize method
ms.assetid: dae64c5f-5b54-40c3-b32f-ec3b16c093f7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8fbfc274b3508cbbd2658a5c352c12fab919996b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53837948"
---
# <a name="idebugmemorybytes2getsize"></a>IDebugMemoryBytes2::GetSize
检索大小 （字节） 的内存由此[IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetSize(   
   UINT64* pqwSize  
);  
```  
  
```csharp  
int GetSize(  
   out ulong pqwSize  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pqwSize`  
 [out]返回的大小，以字节为单位的内存空间。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)