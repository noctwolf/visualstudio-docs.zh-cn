---
title: THREADSTATE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- THREADSTATE
helpviewer_keywords:
- THREADSTATE enumeration
ms.assetid: 62efdd7c-25b1-4fd3-9d06-ac1830a418a9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d980eda1cb876392342e8eef7c49ec68456c8908
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53951067"
---
# <a name="threadstate"></a>THREADSTATE
指定线程的状态。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_THREADSTATE {   
   THREADSTATE_RUNNING = 0x0001,  
   THREADSTATE_STOPPED = 0x0002,  
   THREADSTATE_FRESH   = 0x0003,  
   THREADSTATE_DEAD    = 0x0004,  
   THREADSTATE_FROZEN  = 0x0005  
};  
typedef DWORD THREADSTATE;  
```  
  
```csharp  
public enum enum_THREADSTATE {   
   THREADSTATE_RUNNING = 0x0001,  
   THREADSTATE_STOPPED = 0x0002,  
   THREADSTATE_FRESH   = 0x0003,  
   THREADSTATE_DEAD    = 0x0004,  
   THREADSTATE_FROZEN  = 0x0005  
};  
```  
  
## <a name="members"></a>成员  
 THREADSTATE_RUNNING  
 指示该线程正在运行。  
  
 THREADSTATE_STOPPED  
 指示该线程已因断点而停止。  
  
 THREADSTATE_FRESH  
 指示线程已创建但尚未运行代码。  
  
 THREADSTATE_DEAD  
 指示线程出现故障。  
  
 THREADSTATE_FROZEN  
 指示该线程已冻结 （可以执行任何执行）。  
  
## <a name="remarks"></a>备注  
 用于`dwThreadState`字段[THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)结构。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)