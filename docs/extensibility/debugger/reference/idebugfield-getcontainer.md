---
title: IDebugField::GetContainer |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugField::GetContainer
helpviewer_keywords:
- IDebugField::GetContainer method
ms.assetid: 6d6c8213-6181-4adf-9584-3e4cac163dd8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3bf1aea1291b8d92d2ebdfcb35f4c6eeb5125f77
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54983882"
---
# <a name="idebugfieldgetcontainer"></a>IDebugField::GetContainer
此方法获取字段的容器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetContainer(   
   IDebugContainerField** ppContainerField  
);  
```  
  
```csharp  
int GetContainer(  
   out IDebugContainerField ppContainerField  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppContainerField`  
 [out]由返回的容器[IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)接口。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 如果此字段不包含容器，返回的`ppContainerField`值将为 null 值。  
  
## <a name="see-also"></a>请参阅  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)