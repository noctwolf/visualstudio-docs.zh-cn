---
title: IDebugManagedObject::SetFromManagedObject | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugManagedObject::SetFromManagedObject
helpviewer_keywords:
- IDebugManagedObject::SetFromManagedObject method
ms.assetid: 8700ee8d-2704-4580-bccc-046837a24edd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a760bb14ea1749e359b5f9deacb6e5918a42423f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54974391"
---
# <a name="idebugmanagedobjectsetfrommanagedobject"></a>IDebugManagedObject::SetFromManagedObject
从作为参数提供的值类的实例设置的值类对象的实例的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetFromManagedObject(   
   IUnknown* pManagedObject  
);  
```  
  
```csharp  
int SetFromManagedObject(  
   object pManagedObject  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pManagedObject`  
 [in]一个表示包含新值的托管的对象的接口。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 使用此方法可以更改托管的对象，由表示[IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)对象。  
  
## <a name="see-also"></a>请参阅  
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)