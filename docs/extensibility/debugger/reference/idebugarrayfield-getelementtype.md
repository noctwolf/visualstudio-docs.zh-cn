---
title: IDebugArrayField::GetElementType |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugArrayField::GetElementType
helpviewer_keywords:
- IDebugArrayField::GetElementType method
ms.assetid: c46bf625-0a48-4cbb-8f1f-286356f2c065
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6daf0fc7a7aa2f283728210003254885345d69ee
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54954795"
---
# <a name="idebugarrayfieldgetelementtype"></a>IDebugArrayField::GetElementType
获取数组中元素的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetElementType(   
   IDebugField** ppType  
);  
```  
  
```csharp  
int GetElementType(  
   out IDebugField ppType  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppType`  
 [out]返回[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)描述的元素的类型的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)对象假定数组的所有元素都具有相同的类型。  
  
## <a name="see-also"></a>请参阅  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)