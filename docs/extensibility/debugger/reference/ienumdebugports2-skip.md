---
title: IEnumDebugPorts2::Skip | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPorts2::Skip
helpviewer_keywords:
- IEnumDebugPorts2::Skip
ms.assetid: a837383f-7b39-4e06-b336-f1715b073dbe
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 11af4b55aeb3dbc0f03c904d2d3e29fba4f6f7bb
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65225710"
---
# <a name="ienumdebugports2skip"></a>IEnumDebugPorts2::Skip
跳过指定数量的元素。

## <a name="syntax"></a>语法

```cpp
HRESULT Skip(
   ULONG celt
);
```

```csharp
int Skip(
   uint celt
);
```

## <a name="parameters"></a>参数
 `celt`\

 [in]要跳过的元素数。

## <a name="return-value"></a>返回值
 如果成功，则返回 `S_OK`。 返回`S_FALSE`如果`celt`大于剩余的元素数; 否则，返回错误代码。

## <a name="remarks"></a>备注
 如果`celt`指定的值数比大剩余元素的枚举设置为结束和`S_FALSE`返回。

## <a name="see-also"></a>请参阅
- [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)