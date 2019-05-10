---
title: PARSEFLAGS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PARSEFLAGS
helpviewer_keywords:
- PARSEFLAGS enumeration
ms.assetid: 47943f0a-54cb-4493-a62e-5dba97bd4c35
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e5d298add846a7f3b7baf566f3c31e16c68b8dc5
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "65460842"
---
# <a name="parseflags"></a>PARSEFLAGS
指定如何分析表达式。

## <a name="syntax"></a>语法

```cpp
enum enum_PARSEFLAGS { 
   PARSE_EXPRESSION            = 0x0001,
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000
};
typedef DWORD PARSEFLAGS;
```

```csharp
public enum enum_PARSEFLAGS { 
   PARSE_EXPRESSION            = 0x0001,
   PARSE_FUNCTION_AS_ADDRESS   = 0x0002,
   PARSE_DESIGN_TIME_EXPR_EVAL = 0x1000
};
```

## <a name="fields"></a>字段
 `PARSE_EXPRESSION`\
 指示该表达式不是一个语句。

 `PARSE_FUNCTION_AS_ADDRESS`\
 指示表达式是以进行分析 （和更高版本评估） 地址。

 `PARSE_DESIGN_TIME_EXPR_EVAL`\
 指示在设计时正在分析表达式 （即，设计器打开时）。

## <a name="remarks"></a>备注
 作为参数传递给[ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)并[分析](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)方法。

## <a name="requirements"></a>要求
 标头： msdbg.h

 命名空间:Microsoft.VisualStudio.Debugger.Interop

 程序集：Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅
- [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [ParseText](../../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)
- [分析](../../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md)