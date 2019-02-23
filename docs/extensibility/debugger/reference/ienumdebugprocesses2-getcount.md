---
title: IEnumDebugProcesses2::GetCount | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugProcesses2::GetCount
helpviewer_keywords:
- IEnumDebugProcesses2::GetCount
ms.assetid: 5dc3e36c-46e5-4556-bf41-1870aa67d2a0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9ef74e226dd2c84a12ef76c25b87b05fb8a21824
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56711756"
---
# <a name="ienumdebugprocesses2getcount"></a>IEnumDebugProcesses2::GetCount
枚举中返回元素的数。

## <a name="syntax"></a>语法

```cpp
HRESULT GetCount(
   ULONG* pcelt
);
```

```csharp
int GetCount(
   out uint pcelt
);
```

#### <a name="parameters"></a>参数
 `pcelt`

 [out]枚举中返回元素的数。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 此方法不是惯用的 COM 枚举接口，只有指定的一部分`Next`， `Clone`， `Skip`，和`Reset`方法需要实现。

## <a name="see-also"></a>请参阅
- [IEnumDebugProcesses2](../../../extensibility/debugger/reference/ienumdebugprocesses2.md)