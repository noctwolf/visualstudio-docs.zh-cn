---
title: IDebugObject::GetManagedDebugObject | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject::GetManagedDebugObject
helpviewer_keywords:
- IDebugObject::GetManagedDebugObject method
ms.assetid: cb89692e-7657-47ff-846d-311943521951
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: b0721e8f8a30a8736f6d52ea61e02b9a93821a98
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66203015"
---
# <a name="idebugobjectgetmanageddebugobject"></a>IDebugObject::GetManagedDebugObject
调试引擎的地址空间中创建托管对象的副本。

## <a name="syntax"></a>语法

```cpp
HRESULT GetManagedDebugObject( 
   IDebugManagedObject** ppObject
);
```

```csharp
int GetManagedDebugObject(
   out IDebugManagedObject ppObject
);
```

## <a name="parameters"></a>参数
`ppObject`\
[out]返回[IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)对象，表示新创建的托管的对象。

## <a name="return-value"></a>返回值
 如果成功，则返回 S_OK;否则，返回错误代码。 如果此返回 E_FAIL [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)不表示托管的值类实例。

## <a name="remarks"></a>备注
 这[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象必须代表托管的值类实例，如`System.Decimal`实例。 通过让本地副本，而调用的开销[Evaluate](../../../extensibility/debugger/reference/idebugfunctionobject-evaluate.md)被消除。

## <a name="see-also"></a>请参阅
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
- [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)