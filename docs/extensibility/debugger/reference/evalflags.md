---
title: EVALFLAGS |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- EVALFLAGS
helpviewer_keywords:
- EVALFLAGS enumeration
ms.assetid: 7b2cb14a-511a-4fef-9e4f-308139719fba
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7c718414749bb6c748f25fb90837644fe984a274
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="evalflags"></a>EVALFLAGS
指定可控制表达式计算的标志。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_EVALFLAGS {  
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
public enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
}  
```  
  
## <a name="members"></a>成员  
 EVAL_RETURNVALUE  
 指定返回的值，如果有的话，进行计算。  
  
 EVAL_NOSIDEEFFECTS  
 指定不允许副作用。  
  
 EVAL_ALLOWBPS  
 指定在断点上的停止。  
  
 EVAL_ALLOWERRORREPORT  
 指定错误报告到主机，以允许。 主要用于在 Internet Explorer 中的脚本中的表达式计算。  
  
 EVAL_FUNCTION_AS_ADDRESS  
 强制函数计算结果为地址，而不是调用该函数。  
  
 EVAL_NOFUNCEVAL  
 正在评估会阻止函数。 例如，考虑`int`令牌在表达式中`myExpression(int) + 10`。 为地址，但不是作为一个值，此函数可以正确评估。  
  
 EVAL_NOEVENTS  
 标记以指示在表达式计算过程中发生的事件应将不发送到会话调试管理器 (SDM) 或 IDE。  
  
## <a name="remarks"></a>备注  
 这些标志传递的自变量作为[EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)和[EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)方法。  
  
 可能与按位 OR 组合这些标志。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)