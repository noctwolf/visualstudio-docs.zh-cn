---
title: IDebugProgram3 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugProgram3 interface
ms.assetid: 4301ba23-c00c-4ce5-8b1e-3f27da312034
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dcc1b6071fbe83b6752b1b2b1ac2218979dbc55f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56684291"
---
# <a name="idebugprogram3"></a>IDebugProgram3
此接口表示一个程序，在进程中运行并扩展了[Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md)通过提供线程信息。

## <a name="syntax"></a>语法

```
IDebugProgram3 : IDebugProgram3
```

## <a name="notes-for-implementers"></a>实施者的说明
 调试引擎 (DE) 和自定义端口提供程序实现此接口来表示在进程中的程序。 会话调试管理器 (SDM) 也实现此接口将信息提供给[附加](../../../extensibility/debugger/reference/idebugprogram2-attach.md)。

## <a name="notes-for-callers"></a>调用方的说明
 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)事件返回此接口的新程序。 此接口还用作多个接口上的许多方法参数。

## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法
 下表显示的方法`IDebugProgram3`。

|方法|描述|
|------------|-----------------|
|[ExecuteOnThread](../../../extensibility/debugger/reference/idebugprogram3-executeonthread.md)|执行程序。 线程将返回以授予用户查看哪个线程执行时的调试程序信息。|

## <a name="requirements"></a>要求
 标头： msdbg.h

 命名空间:Microsoft.VisualStudio.Debugger.Interop

 程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="remarks"></a>备注
 程序是运行在特定的运行时体系结构中，而进程组成一个或多个程序的线程容器。

## <a name="see-also"></a>请参阅
- [核心接口](../../../extensibility/debugger/reference/core-interfaces.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [GetProgram](../../../extensibility/debugger/reference/idebugthread2-getprogram.md)
- [下一页](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md)
- [Event](../../../extensibility/debugger/reference/idebugportevents2-event.md)
- [附加](../../../extensibility/debugger/reference/idebugengine2-attach.md)
- [DestroyProgram](../../../extensibility/debugger/reference/idebugengine2-destroyprogram.md)
- [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)
- [Attach_V7](../../../extensibility/debugger/reference/idebugprogramnode2-attach-v7.md)