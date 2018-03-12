---
title: "IDebugObject::IsEqual |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugObject::IsEqual
helpviewer_keywords:
- IDebugObject::IsEqual method
ms.assetid: 4b76e663-ef2e-41ff-9be1-bf26d666a34a
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2af7ef11a142442b97dbb5d6a4d0545bf118da39
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugobjectisequal"></a>IDebugObject::IsEqual
比较对象与此对象。  
  
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
 [in][IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象表示要比较的对象。  
  
 `pfIsEqual`  
 [out]返回非零 (`TRUE`) 如果对象的值相等; 否则为返回零 (`FALSE`)。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 通常情况下，此方法可以比较所表示的值的地址`pObject`参数，这[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象; 如果地址是否相等，则对象可被视为相等。  
  
## <a name="see-also"></a>请参阅  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)