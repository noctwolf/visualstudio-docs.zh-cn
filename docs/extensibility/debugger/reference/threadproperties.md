---
title: THREADPROPERTIES |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- THREADPROPERTIES
helpviewer_keywords:
- THREADPROPERTIES structure
ms.assetid: 7d397207-db03-4ec0-9f79-3794056ed89f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e4079c688358f3e7deedd28b5eb05e556192bfe6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31125746"
---
# <a name="threadproperties"></a>THREADPROPERTIES
介绍在线程的属性。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _tagTHREADPROPERTIES {   
   THREADPROPERTY_FIELDS dwFields;  
   DWORD                 dwThreadId;  
   DWORD                 dwSuspendCount;  
   DWORD                 dwThreadState;  
   BSTR                  bstrPriority;  
   BSTR                  bstrName;  
   BSTR                  bstrLocation;  
} THREADPROPERTIES;  
```  
  
```csharp  
public struct THREADPROPERTIES {   
   public uint   dwFields;  
   public uint   dwThreadId;  
   public uint   dwSuspendCount;  
   public uint   dwThreadState;  
   public string bstrPriority;  
   public string bstrName;  
   public string bstrLocation;  
};  
```  
  
## <a name="members"></a>成员  
 dwFields  
 中的标志的组合[THREADPROPERTY_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md)描述此结构中的哪些字段有效的枚举。  
  
 dwThreadId  
 线程 id。  
  
 dwSuspendCount  
 线程挂起计数。  
  
 dwThreadState  
 取值范围为[线程](../../../extensibility/debugger/reference/threadstate.md)枚举，该值指示操作系统线程的状态。  
  
 bstrPriority  
 一个字符串，指定线程的优先级。例如，"高于正常"、"Normal"或者"时间关键"。  
  
 bstName  
 线程名称中。  
  
 bstrLocation  
 线程位置 （通常最顶层的堆栈帧），通常表示为当前暂停执行方法的名称。  
  
## <a name="remarks"></a>备注  
 此结构通过调用填充[GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)方法。 因此返回的信息通常用于填充**线程**窗口。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)   
 [THREADPROPERTY_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md)   
 [THREADSTATE](../../../extensibility/debugger/reference/threadstate.md)