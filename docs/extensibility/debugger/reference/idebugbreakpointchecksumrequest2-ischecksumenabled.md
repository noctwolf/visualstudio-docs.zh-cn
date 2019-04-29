---
title: IDebugBreakpointChecksumRequest2::IsChecksumEnabled |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugBreakpointChecksumRequest2::IsChecksumEnabled
ms.assetid: 8b1853b5-745c-4cd6-88a9-ce0673971bb0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7bf2bf2807d6433011005b87c40fed22a5c434bd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62877076"
---
# <a name="idebugbreakpointchecksumrequest2ischecksumenabled"></a>IDebugBreakpointChecksumRequest2::IsChecksumEnabled
确定是否为本文档启用校验和。

## <a name="syntax"></a>语法

```cpp
HRESULT IsChecksumEnabled(
   BOOL *pfChecksumEnabled
);
```

```csharp
public int IsChecksumEnabled(
   out int pfChecksumEnabled
);
```

#### <a name="parameters"></a>参数
 `pfChecksumEnabled`

 [out]如果已启用校验和; 将返回 TRUE否则，返回 FALSE。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="see-also"></a>请参阅
- [IDebugBreakpointChecksumRequest2](../../../extensibility/debugger/reference/idebugbreakpointchecksumrequest2.md)