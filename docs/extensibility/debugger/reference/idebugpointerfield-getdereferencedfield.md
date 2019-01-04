---
title: IDebugPointerField::GetDereferencedField |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPointerField::GetDereferencedField
helpviewer_keywords:
- IDebugPointerField::GetDereferencedField method
ms.assetid: 8de988ab-cd79-4287-be72-3c900f2fe407
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 58f590f88344a76095156b71c4c535b158582dc3
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53844585"
---
# <a name="idebugpointerfieldgetdereferencedfield"></a>IDebugPointerField::GetDereferencedField
此方法返回的此指针对象所指向的对象的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetDereferencedField(  
   IDebugField** ppField  
);  
```  
  
```csharp  
int GetDereferencedField(  
   out IDebugField ppField  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppField`  
 [out]返回[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)描述类型的目标对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 例如，如果[IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)对象指向一个整数， [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)此方法返回的类型描述该整数类型。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)