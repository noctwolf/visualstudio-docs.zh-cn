---
title: DEBUG_REASON |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DEBUG_REASON
helpviewer_keywords:
- DEBUG_REASON enumeration
ms.assetid: ad2ee898-8648-4671-9078-d32873862346
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5842b79e6dd38ed99a7a255b4164762b1dd1b68b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53867337"
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
 DEBUG_REASON_ERROR  
 发生了非特定错误 （这用作默认条件时没有其他原因，调整）。  
  
 DEBUG_REASON_USER_LAUNCHED  
 该过程是在用户的请求时启动的。  
  
 DEBUG_REASON_USER_ATTACHED  
 已在运行的进程已附加到用户。  
  
 DEBUG_REASON_AUTO_ATTACHED  
 程序启动时，该过程是自动附加到。  
  
 DEBUG_REASON_CAUSALITY  
 由于已启动进程*中实时*(JIT) 调试事件。  
  
## <a name="remarks"></a>备注  
 返回从[GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)