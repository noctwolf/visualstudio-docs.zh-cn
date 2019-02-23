---
title: IDebugBreakpointRequest3::GetRequestInfo2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugBreakpointRequest3::GetRequestInfo2
helpviewer_keywords:
- IDebugBreakpointRequest3::GetRequestInfo2
ms.assetid: 33942e4a-0a0a-49e8-a693-004954f6d38a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 06458649d091be104c5509e37aa35029a119c84f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56697136"
---
# <a name="idebugbreakpointrequest3getrequestinfo2"></a>IDebugBreakpointRequest3::GetRequestInfo2
此方法获取描述此断点请求的断点请求信息。

## <a name="syntax"></a>语法

```cpp
HRESULT GetRequestInfo2(
   BPREQI_FIELDS      dwFields,
   BP_REQUEST_INFO2*  bBPRequestInfo
);
```

```csharp
int GetRequestInfo2(
   enum_BPREQI_FIELDS  dwFields,
   BP_REQUEST_INFO2[]  bBPRequestInfo
);
```

#### <a name="parameters"></a>参数
 `dwFields`

 [in]中的标志的组合[BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md)枚举，用于确定哪些字段的`pBPRequestInfo`要填充的。

 `bBPRequestInfo`

 [out][BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)要填充的结构。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为将返回错误代码。

## <a name="remarks"></a>备注
 在此请求中不是从返回的详细信息[GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)方法。

## <a name="see-also"></a>请参阅
- [IDebugBreakpointRequest3](../../../extensibility/debugger/reference/idebugbreakpointrequest3.md)
- [GetRequestInfo](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getrequestinfo.md)
- [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
- [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md)