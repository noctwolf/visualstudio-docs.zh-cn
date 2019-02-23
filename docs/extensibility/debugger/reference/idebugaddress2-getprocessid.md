---
title: IDebugAddress2::GetProcessID | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugAddress2::GetProcessID
helpviewer_keywords:
- IDebugAddress2::GetProcessID method
ms.assetid: 2c18889d-074a-4b95-87b4-bf1a067f44ed
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3d2fce11c4ddd5a2ca882749ff4ae4a9b3ee0434
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56723313"
---
# <a name="idebugaddress2getprocessid"></a>IDebugAddress2::GetProcessID
检索由此对象所属的进程 ID [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)接口。

## <a name="syntax"></a>语法

```cpp
HRESULT GetProcessID (
   DWORD* pProcID
);
```

```csharp
int GetProcessID (
   out uint pProcID
);
```

#### <a name="parameters"></a>参数
 `pProcID`

 [out]进程 id。

## <a name="return-value"></a>返回值
 如果成功，则返回 S_OK;否则，返回错误代码。

## <a name="see-also"></a>请参阅
- [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)