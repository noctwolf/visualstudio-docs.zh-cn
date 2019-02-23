---
title: BP_RESOLUTION_INFO | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BP_RESOLUTION_INFO
helpviewer_keywords:
- BP_RESOLUTION_INFO structure
ms.assetid: ba0c162a-61e8-4a0b-811f-4c1d8a5d82f0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 79104bf245221c14a27593665c1a4b2cd8cedaa0
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56707219"
---
# <a name="bpresolutioninfo"></a>BP_RESOLUTION_INFO
介绍代码断点或数据断点的绑定的断点信息。

## <a name="syntax"></a>语法

```cpp
typedef struct _BP_RESOLUTION_INFO {
    BPRESI_FIELDS          dwFields;
    BP_RESOLUTION_LOCATION bpResLocation;
    IDebugProgram2*        pProgram;
    IDebugThread2*         pThread;
} BP_RESOLUTION_INFO;
```

```csharp
public struct BP_RESOLUTION_INFO {
    public uint                   dwFields;
    public BP_RESOLUTION_LOCATION bpResLocation;
    public IDebugProgram2         pProgram;
    public IDebugThread2          pThread;
};
```

## <a name="members"></a>成员
`dwFields` 中的标志的集合[BPRESI_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md)填充指定的字段的枚举。

`bpResLocation` [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md)结构，它在代码或数据中指定的断点的位置。

`pProgram` [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)表示应用程序发生断点错误的对象。

`pThread` [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)对象，表示包含断点错误的应用程序正在其中运行的线程。

## <a name="remarks"></a>备注
返回此结构[GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)。

## <a name="requirements"></a>要求
标头： msdbg.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)
- [GetResolutionInfo](../../../extensibility/debugger/reference/idebugbreakpointresolution2-getresolutioninfo.md)
- [BPRESI_FIELDS](../../../extensibility/debugger/reference/bpresi-fields.md)
- [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)
