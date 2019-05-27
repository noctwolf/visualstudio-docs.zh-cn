---
title: IDebugCanStopEvent2::GetReason | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCanStopEvent2::GetReason
helpviewer_keywords:
- IDebugCanStopEvent2::GetReason
ms.assetid: f5de31ca-7b8d-4029-9cf9-ba860ac66af6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e1bfc8b813f1016f3c040d47120675f881b92020
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66203144"
---
# <a name="idebugcanstopevent2getreason"></a>IDebugCanStopEvent2::GetReason
获取调试引擎 (DE) 是为什么想要停止的原因。

## <a name="syntax"></a>语法

```cpp
HRESULT GetReason( 
   CANSTOP_REASON* pcr
);
```

```csharp
int GetReason( 
   out enum_CANSTOP_REASON pcr
);
```

## <a name="parameters"></a>参数
`pcr`\
[out]返回一个值从[CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md)介绍了此事件的原因的枚举。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 此方法通常称为之前[CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)方法，以便调用方可以确定是否将传递非零值 (`TRUE`) 到`IDebugCanStopEvent2::CanStop`方法。

 正在停止的原因可以是`CANSTOP_ENTRYPOINT`，这意味着 DE 已达到的入口点，或`CANSTOP_STEPIN`，这意味着 DE 单步执行函数。

## <a name="see-also"></a>请参阅
- [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)
- [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md)
- [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)