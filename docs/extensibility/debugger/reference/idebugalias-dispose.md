---
title: IDebugAlias::Dispose |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAlias::Dispose
helpviewer_keywords:
- IDebugAlias::Dispose method
ms.assetid: e84909a4-d378-4f48-bf25-2c014c77c8e3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d35b5819aa0354581721f02a931aa7bdf679b70d
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56714951"
---
# <a name="idebugaliasdispose"></a>IDebugAlias::Dispose
将标记为删除此别名。

## <a name="syntax"></a>语法

```cpp
HRESULT Dispose();
```

```csharp
int Dispose();
```

#### <a name="parameters"></a>参数
 无。

## <a name="return-value"></a>返回值
 如果成功，则返回 S_OK;否则，返回错误代码。

## <a name="remarks"></a>备注
 一旦调用此方法，该别名不再可用。

## <a name="see-also"></a>请参阅
- [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md)