---
title: IEnumDebugCodeContexts2::GetCount | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugCodeContexts2::GetCount
helpviewer_keywords:
- IEnumDebugCodeContexts2::GetCount
ms.assetid: 74c52fcf-688c-40df-9acd-29b3b84e6216
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f9cf2aef80f833961b9af13da4fa9f9b97e43435
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56681055"
---
# <a name="ienumdebugcodecontexts2getcount"></a>IEnumDebugCodeContexts2::GetCount
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
- [IEnumDebugCodeContexts2](../../../extensibility/debugger/reference/ienumdebugcodecontexts2.md)