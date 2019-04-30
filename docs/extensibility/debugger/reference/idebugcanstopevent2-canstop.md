---
title: IDebugCanStopEvent2::CanStop |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCanStopEvent2::CanStop
helpviewer_keywords:
- IDebugCanStopEvent2::CanStop
ms.assetid: 7d61adbe-6b3d-41f3-86a1-45d9cc01a7f8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 307b6d25f2e45276ead7c4b360ae191a01059104
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62876964"
---
# <a name="idebugcanstopevent2canstop"></a>IDebugCanStopEvent2::CanStop
通知在当前代码位置停止，或只需继续执行调试引擎 (DE)。

## <a name="syntax"></a>语法

```cpp
HRESULT CanStop ( 
   BOOL fCanStop
);
```

```csharp
int CanStop ( 
   int fCanStop
);
```

#### <a name="parameters"></a>参数
 `fCanStop`

 [in]非零 (`TRUE`) 如果 DE 应停止在当前代码位置; 否则为零 (`FALSE`)。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="remarks"></a>备注
 此事件的接收方通常会调用[GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)方法，以确定 DE 想要停止的原因，然后调用`IDebugCanStopEvent2::CanStop`与适当的响应的方法。

 如果 DE 停止，它将发送事件，介绍了停止的原因。 通常有两个发送的事件，表示用户或信号中断[IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)接口，并且表示的断点事件[IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)接口。

## <a name="see-also"></a>请参阅
- [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)
- [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)
- [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)
- [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)