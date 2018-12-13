---
title: IEnumDebugReferenceInfo2::Next |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEnumDebugReferenceInfo2::Next
helpviewer_keywords:
- IEnumDebugReferenceInfo2::Next
ms.assetid: 70b31a57-1701-4757-9e7e-63ec60a71b3c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ccb977b637f15493ca64c6cb817565279888281f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49934166"
---
# <a name="ienumdebugreferenceinfo2next"></a>IEnumDebugReferenceInfo2::Next
枚举中返回下一组元素。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Next(  
   ULONG                   celt,  
   DEBUG_REFERENCE_INFO ** rgelt,  
   ULONG*                  pceltFetched  
);  
```  
  
```csharp  
int Next(  
   uint                   celt,  
   DEBUG_REFERENCE_INFO[] rgelt,  
   ref uint               pceltFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 [in]要检索的元素数。 此外可以指定的最大大小`rgelt`数组。  
  
 `rgelt`  
 [in、 out]数组[DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)要填充的元素。  
  
 `pceltFetched`  
 [out]返回中实际返回的元素数目`rgelt`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果无法返回请求的元素数少于; 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugReferenceInfo2](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)