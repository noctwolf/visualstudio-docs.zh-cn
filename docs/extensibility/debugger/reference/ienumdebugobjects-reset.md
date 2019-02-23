---
title: IEnumDebugObjects::Reset | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugObjects::Reset
helpviewer_keywords:
- IEnumDebugObjects::Reset method
ms.assetid: 4a245e47-cc39-4177-b83d-083ea0e3190f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ebeef5502787ad5ab745d72e42205d86320a8f20
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56706764"
---
# <a name="ienumdebugobjectsreset"></a>IEnumDebugObjects::Reset
此方法将枚举重置为第一个元素。

## <a name="syntax"></a>语法

```cpp
HRESULT Reset(void);
```

```csharp
int Reset();
```

#### <a name="parameters"></a>参数
 无

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 调用此方法下, 一步调用后[下一步](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)返回枚举的第一个元素。

## <a name="see-also"></a>请参阅
- [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md)
- [下一页](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)