---
title: DEBUG_REASON | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DEBUG_REASON
helpviewer_keywords:
- DEBUG_REASON enumeration
ms.assetid: ad2ee898-8648-4671-9078-d32873862346
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 03b2db1fd58af6a8b2f8a57846e7753cdbc82352
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56707258"
---
# <a name="debugreason"></a>DEBUG_REASON
指定用于调试启动进程时为什么。

## <a name="syntax"></a>语法

```cpp
enum enum_DEBUG_REASON {
    DEBUG_REASON_ERROR         = 0,
    DEBUG_REASON_USER_LAUNCHED = 1,
    DEBUG_REASON_USER_ATTACHED = 2,
    DEBUG_REASON_AUTO_ATTACHED = 3,
    DEBUG_REASON_CAUSALITY     = 4
};
typedef DWORD DEBUG_REASON;
```

```csharp
public enum enum_DEBUG_REASON {
    DEBUG_REASON_ERROR         = 0,
    DEBUG_REASON_USER_LAUNCHED = 1,
    DEBUG_REASON_USER_ATTACHED = 2,
    DEBUG_REASON_AUTO_ATTACHED = 3,
    DEBUG_REASON_CAUSALITY     = 4
};
```

#### <a name="parameters"></a>参数
DEBUG_REASON_ERROR 一个非特定的错误 （这用作默认条件时没有其他原因，调整）。

DEBUG_REASON_USER_LAUNCHED 过程是在用户的请求时启动的。

DEBUG_REASON_USER_ATTACHED 已经运行的进程已附加到用户。

DEBUG_REASON_AUTO_ATTACHED 过程已自动附加到程序启动时。

由于已启动进程的 DEBUG_REASON_CAUSALITY*中实时*(JIT) 调试事件。

## <a name="remarks"></a>备注
返回从[GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)方法。

## <a name="requirements"></a>要求
标头： msdbg.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)
