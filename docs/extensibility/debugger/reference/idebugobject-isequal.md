---
title: IDebugObject::IsEqual |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugObject::IsEqual
helpviewer_keywords:
- IDebugObject::IsEqual method
ms.assetid: 4b76e663-ef2e-41ff-9be1-bf26d666a34a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 91e84d47f7fc60e60c3c7fb58ba66bc0a00daf30
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49839994"
---
# <a name="idebugobjectisequal"></a>IDebugObject::IsEqual
将与此对象的对象进行比较。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT IsEqual(   
   IDebugObject* pObject,  
   BOOL*         pfIsEqual  
);  
```  
  
```csharp  
int IsEqual(  
   IDebugObject pObject,  
   out int      pfIsEqual  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pObject`  
 [in][IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象，表示要比较的对象。  
  
 `pfIsEqual`  
 [out]返回非零值 (`TRUE`) 的对象的值是相等; 否则为如果返回零 (`FALSE`)。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 通常情况下，此方法可以比较所表示的值的地址`pObject`参数，这[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象; 如果地址相等，则对象可被视为相等。  
  
## <a name="see-also"></a>请参阅  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)