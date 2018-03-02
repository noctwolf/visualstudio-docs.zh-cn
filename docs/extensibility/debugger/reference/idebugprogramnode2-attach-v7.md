---
title: IDebugProgramNode2::Attach_V7 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugProgramNode2::Attach
helpviewer_keywords:
- IDebugProgramNode2::Attach_V7
- IDebugProgramNode2::Attach
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7db57be153634476b8c0ba5ff6b6b1273ef190be
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="idebugprogramnode2attachv7"></a>IDebugProgramNode2::Attach_V7

> [!Note]
> 已弃用。 请勿使用。

## <a name="syntax"></a>语法

```cpp
HRESULT Attach_V7 (
   IDebugProgram2*       pMDMProgram,
   IDebugEventCallback2* pCallback,
   DWORD                 dwReason
);
```

```csharp
int Attach_V7 (
   IDebugProgram2       pMDMProgram,
   IDebugEventCallback2 pCallback,
   uint                 dwReason
);
```

#### <a name="parameters"></a>参数

`pMDMProgram` [in][IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)表示要将附加到的程序的接口。

 `pCallback` [in][IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)接口，用于将调试事件发送到 SDM。

 `dwReason` [in]取值范围为[ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md)枚举，用于指定附加的原因。

## <a name="return-value"></a>返回值

实现应始终返回`E_NOTIMPL`。

## <a name="remarks"></a>备注

> [!WARNING]
> 截至 Visual Studio 2005 中，此方法不再使用，应始终返回`E_NOTIMPL`。 请参阅[IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)接口有关的备用方法，如果程序节点需要指示不能将它附加到或程序节点只在将程序设置`GUID`。 否则，实现[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)方法。

## <a name="prior-to-visual-studio-2005"></a>在 Visual Studio 2005 之前

此方法必须仅当 DE 运行被调试的程序的地址空间中实现。 否则，此方法应返回`S_FALSE`。

当调用此方法时，必须发送 DE [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)事件对象，如果它不已发送的此实例[IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)接口，以及[IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)和[IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)事件对象。 [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)事件对象然后发送，如果`dwReason`参数是`ATTACH_REASON_LAUNCH`。

必须调用 DE [GetProgramId](../../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)方法[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)通过提供对象[IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)事件对象，并必须存储该程序的 GUID中的实例数据`IDebugProgram2`由 DE 实现的对象。

## <a name="see-also"></a>请参阅

[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)  
[IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)  
[附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)  
[IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)  
[IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)  
[IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)  
[IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)  
[IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)  
[IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)  
[ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md)