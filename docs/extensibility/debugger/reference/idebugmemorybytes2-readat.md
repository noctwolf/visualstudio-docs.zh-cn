---
title: IDebugMemoryBytes2::ReadAt | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugMemoryBytes2::ReadAt
helpviewer_keywords:
- IDebugMemoryBytes2::ReadAt method
- ReadAt method
ms.assetid: b413684d-4155-4bd4-ae30-ffa512243b5f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 16c5df12b268fb53ebd5b6174cbf9225a868f048
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55023624"
---
# <a name="idebugmemorybytes2readat"></a>IDebugMemoryBytes2::ReadAt
读取给定位置处开始的字节序列。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ReadAt(   
   IDebugMemoryContext2* pStartContext,  
   DWORD                 dwCount,  
   BYTE*                 rgbMemory,  
   DWORD*                pdwRead,  
   DWORD*                pdwUnreadable  
);  
```  
  
```csharp  
int ReadAt(  
   IDebugMemoryContext2 pStartContext,  
   uint                 dwCount,  
   byte[]               rgbMemory,  
   out uint             pdwRead,  
   ref uint             pdwUnreadable  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pStartContext`  
 [in][IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)对象，它指定位置开始读取字节数。  
  
 `dwCount`  
 [in]要读取的字节数。 此外可以指定的长度`rgbMemory`数组。  
  
 `rgbMemory`  
 [in、 out]实际读取字节填充的数组。  
  
 `pdwRead`  
 [out]返回实际读取的连续字节数。  
  
 `pdwUnreadable`  
 [in、 out]返回不可读字节数。 如果客户端不愿意在不可读字节数可能为 null 值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 如果请求 100 个字节和前 50 个可读下, 一步 20 是不可读取的并剩余 30 可读，则此方法返回：  
  
 *`pdwRead` = 50  
  
 *`pdwUnreadable` = 20  
  
 在这种情况下，因为`*pdwRead + *pdwUnreadable < dwCount`，调用方必须进行额外调用读取剩余 30 个字节的请求的原始 100 并[IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)传入的对象`pStartContext`必须高级参数通过 70。  
  
## <a name="see-also"></a>请参阅  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)