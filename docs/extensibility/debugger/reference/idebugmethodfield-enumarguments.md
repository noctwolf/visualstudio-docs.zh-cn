---
title: IDebugMethodField::EnumArguments |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugMethodField::EnumArguments
helpviewer_keywords:
- IDebugMethodField::EnumArguments method
ms.assetid: 3ab55488-2437-4ff6-a9ae-78ea6d7b23a8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f5d2f02621b91a8a39b38788072f8099178858c0
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66210320"
---
# <a name="idebugmethodfieldenumarguments"></a>IDebugMethodField::EnumArguments
创建调用该方法所需的每个参数的类型的枚举器。

## <a name="syntax"></a>语法

```cpp
HRESULT EnumArguments( 
   IEnumDebugFields** ppParams
);
```

```csharp
int EnumArguments(
   out IEnumDebugFields ppParams
);
```

## <a name="parameters"></a>参数
`ppParams`\
[out]返回[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)对象，表示自变量类型的列表。 如果没有任何自变量，则返回 null 值。

## <a name="return-value"></a>返回值
 如果成功，则返回 S_OK 或如果没有任何自变量，则返回 S_FALSE。 否则，返回错误代码。

## <a name="remarks"></a>备注
 每个元素均[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)对象，表示每个参数的类型。 调用[GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)方法来检索有关每个参数的类型的信息。

 如果参数的名称需要与类型一起使用，然后调用[EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)方法。

## <a name="see-also"></a>请参阅
- [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
- [EnumParameters](../../../extensibility/debugger/reference/idebugmethodfield-enumparameters.md)