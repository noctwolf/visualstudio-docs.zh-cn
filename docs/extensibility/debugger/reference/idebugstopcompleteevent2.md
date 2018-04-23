---
title: IDebugStopCompleteEvent2 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- IDebugStopCompleteEvent2 interface
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ed73821021d3a993507db9925c512119fbb98ca1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2

程序已停止时，调试引擎 (DE) 可以将此可选事件发送到会话调试管理器 (SDM)。

## <a name="syntax"></a>语法

```
IDebugStopCompleteEvent2 : IUnknown
```

## <a name="notes-for-implementers"></a>实施者注意事项

此接口是随 Visual Studio 2005 中引入的。 以前的版本不支持异步停止。

[停止](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)由多进程或多程序方案中 SDM 调用。 当一个程序将停止事件发送到 SDM 时，SDM 请求停止，太其他程序。

停止用于以异步方式通知程序已停止 SDM。 通知 SDM 可用于解释器调试引擎，其中有时没有代码在内部运行调试程序，因此[停止](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)不同步完成。 如果调试引擎想要采用此异步通知时，它必须返回`S_ASYNC_STOP`从[停止](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)。

## <a name="requirements"></a>要求

标头： msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Assembly: Microsoft.VisualStudio.Debugger.Interop.dll