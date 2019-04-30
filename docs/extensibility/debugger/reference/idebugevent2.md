---
title: IDebugEvent2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEvent2
helpviewer_keywords:
- IDebugEvent2 interface
ms.assetid: de3d714d-96fb-4e12-b66b-a75391472153
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7e70767bab6453f3c3d96b58c8be049a832dc6ad
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62920196"
---
# <a name="idebugevent2"></a>IDebugEvent2
此接口用于传达重要的调试信息，例如在断点处停止和非关键信息，例如调试消息。

## <a name="syntax"></a>语法

```
IDebugEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>实施者的说明
 调试引擎 (DE) 和自定义端口提供程序在与所有其他事件接口相同的对象上实现此接口。

## <a name="notes-for-callers"></a>调用方的说明
 使用接口 ID (IID) 自变量提供给[事件](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)或[事件](../../../extensibility/debugger/reference/idebugportevents2-event.md)，会话调试管理器 (SDM) 调用[QueryInterface](/cpp/atl/queryinterface)上`IDebugEvent2`接口，以获得相应的事件接口中。

## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法
 下表显示的方法`IDebugEvent2`。

|方法|描述|
|------------|-----------------|
|[GetAttributes](../../../extensibility/debugger/reference/idebugevent2-getattributes.md)|获取此调试事件的特性。|

## <a name="remarks"></a>备注
 更具体的事件接口，如[IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)，不会从 IDebugEvent2 接口派生，但改为作为同一对象上作为单独的接口实现`IDebugEvent2`。

## <a name="requirements"></a>要求
 标头： msdbg.h

 命名空间:Microsoft.VisualStudio.Debugger.Interop

 程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)
- [Event](../../../extensibility/debugger/reference/idebugportevents2-event.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)