---
title: IDebugPendingBreakpoint2::GetBreakpointRequest | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPendingBreakpoint2::GetBreakpointRequest
helpviewer_keywords:
- IDebugPendingBreakpoint2::GetBreakpointRequest method
- GetBreakpointRequest method
ms.assetid: cb1e36aa-4302-455c-98fb-6638a1ef5c46
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 31c49f81fc28420dc95cc2c263d4bba41d6c041b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62842725"
---
# <a name="idebugpendingbreakpoint2getbreakpointrequest"></a>IDebugPendingBreakpoint2::GetBreakpointRequest
获取用于创建此挂起断点的断点请求。

## <a name="syntax"></a>语法

```cpp
HRESULT GetBreakpointRequest( 
   IDebugBreakpointRequest2** ppBPRequest
);
```

```csharp
int GetBreakpointRequest( 
   out IDebugBreakpointRequest2 ppBPRequest
);
```

#### <a name="parameters"></a>参数
 `ppBPRequest`

 [out]返回[IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)对象，表示用于创建此挂起断点的断点请求。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。 返回`E_BP_DELETED`如果断点已被删除。

## <a name="see-also"></a>请参阅
- [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)
- [IDebugBreakpointRequest2](../../../extensibility/debugger/reference/idebugbreakpointrequest2.md)