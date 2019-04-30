---
title: IEnumDebugProcesses2::Reset | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugProcesses2::Reset
helpviewer_keywords:
- IEnumDebugProcesses2::Reset
ms.assetid: 31cbde4f-0bba-497a-9969-d2c342ef4a7b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d40f40ac792eab1c84c3b195d49cd570ec6f83b8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62914174"
---
# <a name="ienumdebugprocesses2reset"></a>IEnumDebugProcesses2::Reset
将枚举重置为第一个元素。

## <a name="syntax"></a>语法

```cpp
HRESULT Reset(
   void
);
```

```csharp
int Reset();
```

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 调用此方法下, 一步调用后[下一步](../../../extensibility/debugger/reference/ienumdebugprocesses2-next.md)方法返回的第一个元素的枚举。

## <a name="see-also"></a>请参阅
- [IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)