---
title: IDebugManagedObject::SetFromManagedObject | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
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
ms.openlocfilehash: c56ccea9847cc23e45f9877f3d331be723293ee7
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56712185"
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
- [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)