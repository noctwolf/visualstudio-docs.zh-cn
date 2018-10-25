---
title: IDebugManagedObject::SetFromManagedObject |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugManagedObject::SetFromManagedObject
helpviewer_keywords:
- IDebugManagedObject::SetFromManagedObject method
ms.assetid: 8700ee8d-2704-4580-bccc-046837a24edd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: afe3431e282a8cd48ea33851cef00fba116e389a
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49833936"
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