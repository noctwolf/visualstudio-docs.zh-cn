---
title: IDebugPointerObject3::GetPointerAddress |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- GetPointerAddress
- IDebugPointerObject3::GetPointerAddress
ms.assetid: 4cc5af04-9e70-420d-8230-ef3108df6d51
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1066453c502d7935e43f1af467431f9b9a8f80b8
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56706816"
---
# <a name="idebugpointerobject3getpointeraddress"></a>IDebugPointerObject3::GetPointerAddress
检索指针的地址。

## <a name="syntax"></a>语法

```cpp
HRESULT GetPointerAddress (
   UINT64* puAddress
);
```

```csharp
int GetPointerAddress (
   out ulong puAddress
);
```

#### <a name="parameters"></a>参数
 `puAddress`

 [out]返回指针的地址。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="see-also"></a>请参阅
- [IDebugPointerObject3](../../../extensibility/debugger/reference/idebugpointerobject3.md)