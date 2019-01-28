---
title: IEnumDebugCodeContexts2::Next | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugCodeContexts2::Next
helpviewer_keywords:
- IEnumDebugCodeContexts2::Next
ms.assetid: 0d8aa2db-0994-4166-b364-2e25d936fffc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0ead53c33fb1af321fb790f0f7caf9532c9e58b5
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55027858"
---
# <a name="ienumdebugcodecontexts2next"></a>IEnumDebugCodeContexts2::Next
枚举中返回下一组元素。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Next(  
   ULONG                celt,  
   IDebugCodeContext2** rgelt,  
   ULONG*               pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint                 celt,  
   IDebugCodeContext2[] rgelt,  
   ref uint             pceltFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 [in]要检索的元素数。 此外可以指定的最大大小`rgelt`数组。  
  
 `rgelt`  
 [in、 out]数组[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)要填充的元素。  
  
 `pceltFetched`  
 [out]返回中实际返回的元素数目`rgelt`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 `S_OK`。 返回`S_FALSE`如果无法返回请求的元素数少于; 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugCodeContexts2](../../../extensibility/debugger/reference/ienumdebugcodecontexts2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)