---
title: EVALFLAGS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- EVALFLAGS
helpviewer_keywords:
- EVALFLAGS enumeration
ms.assetid: 7b2cb14a-511a-4fef-9e4f-308139719fba
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2a56f7d5fe4741fa887814691eddcf8df93030cd
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "66337882"
---
# <a name="evalflags"></a>EVALFLAGS
指定用于控制表达式求值的标志。

## <a name="syntax"></a>语法

```cpp
enum enum_EVALFLAGS {
    EVAL_RETURNVALUE = 0x0002,
    EVAL_NOSIDEEFFECTS = 0x0004,
    EVAL_ALLOWBPS = 0x0008,
    EVAL_ALLOWERRORREPORT = 0x0010,
    EVAL_FUNCTION_AS_ADDRESS = 0x0040,
    EVAL_NOFUNCEVAL = 0x0080,
    EVAL_NOEVENTS = 0x1000
};
typedef DWORD EVALFLAGS;
```

```csharp
public enum enum_EVALFLAGS {
    EVAL_RETURNVALUE = 0x0002,
    EVAL_NOSIDEEFFECTS = 0x0004,
    EVAL_ALLOWBPS = 0x0008,
    EVAL_ALLOWERRORREPORT = 0x0010,
    EVAL_FUNCTION_AS_ADDRESS = 0x0040,
    EVAL_NOFUNCEVAL = 0x0080,
    EVAL_NOEVENTS = 0x1000
}
```

## <a name="fields"></a>字段
`EVAL_RETURNVALUE`\
指定的计算返回值，如果有的话。

`EVAL_NOSIDEEFFECTS`\
指定不允许副作用。

`EVAL_ALLOWBPS`\
指定断点停止。

`EVAL_ALLOWERRORREPORT`\
指定错误报告到的主机功能，允许。 主要用于在 Internet Explorer 中的脚本中的表达式计算。

`EVAL_FUNCTION_AS_ADDRESS`\
强制函数计算结果为地址，而不是调用该函数。

`EVAL_NOFUNCEVAL`\
防止函数进行计算。 例如，考虑`int`令牌在表达式中`myExpression(int) + 10`。 为地址，但不能作为一个值，此函数可以正确评估。

`EVAL_NOEVENTS`\
一个标志，用于指示会话调试管理器 (SDM) 或 IDE 未发送的表达式计算期间发生的事件。

## <a name="remarks"></a>备注
这些标志作为参数传递[EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)并[EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)方法。

可能会使用按位 OR 组合这些标志。

## <a name="requirements"></a>要求
标头： msdbg.h

命名空间:Microsoft.VisualStudio.Debugger.Interop

程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)
- [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)
