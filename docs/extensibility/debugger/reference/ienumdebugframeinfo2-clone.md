---
title: IEnumDebugFrameInfo2::Clone | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugFrameInfo2::Clone
helpviewer_keywords:
- IEnumDebugFrameInfo2::Clone
ms.assetid: cdd10489-1772-47e3-815f-a6cfd32a3c60
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 7bfd96f1a52fe908e414b16bb7bd003b459059d4
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66208010"
---
# <a name="ienumdebugframeinfo2clone"></a>IEnumDebugFrameInfo2::Clone
返回当前枚举作为一个单独的对象的副本。

## <a name="syntax"></a>语法

```cpp
HRESULT Clone(
   IEnumDebugFrameInfo2** ppEnum
);
```

```csharp
int Clone(
   out IEnumDebugFrameInfo2 ppEnum
);
```

## <a name="parameters"></a>参数
`ppEnum`\
[out]返回此枚举作为一个单独的对象的副本。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 枚举的副本在调用此方法时都具有与原始相同的状态。 但是，该副本的和原始的状态是独立的并且可以单独更改。

## <a name="see-also"></a>请参阅
- [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)