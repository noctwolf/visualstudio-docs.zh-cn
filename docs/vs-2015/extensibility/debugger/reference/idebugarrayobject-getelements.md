---
title: IDebugArrayObject::GetElements |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetElements
helpviewer_keywords:
- IDebugArrayObject::GetElements method
ms.assetid: f6a6262f-5183-46ce-8a45-33ef46088b98
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cad81d76e2fcec01fa50a37fa6ab6cb49cfc79be
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62423694"
---
# <a name="idebugarrayobjectgetelements"></a>IDebugArrayObject::GetElements
获取数组的所有元素的枚举器。

## <a name="syntax"></a>语法

```cpp
HRESULT GetElements( 
   IEnumDebugObjects** ppEnum
);
```

```csharp
int GetElements(
   out IEnumDebugObjects ppEnum
);
```

#### <a name="parameters"></a>参数
 `ppEnum`

 [out]返回[IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)对象，它允许枚举的所有元素。

## <a name="return-value"></a>返回值
 如果成功，则返回 S_OK;否则，返回错误代码。

## <a name="remarks"></a>备注
 或者，使用[GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md)并[GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md)方法来循环访问元素。

## <a name="see-also"></a>请参阅
- [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)