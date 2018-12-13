---
title: EXCEPTION_INFO |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- EXCEPTION_INFO
helpviewer_keywords:
- EXCEPTION_INFO structure
ms.assetid: d046957a-b97d-420b-b46b-c67cbaef709e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4bbefc02a05d03dc966c05941ca08c05cce0a5a5
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49947895"
---
# <a name="exceptioninfo"></a>EXCEPTION_INFO
描述异常或引发由正在调试的程序的运行时错误。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct tagEXCEPTION_INFO {   
   IDebugProgram2* pProgram;  
   BSTR            bstrProgramName;  
   BSTR            bstrExceptionName;  
   DWORD           dwCode;  
   EXCEPTION_STATE dwState;  
   GUID            guidType;  
} EXCEPTION_INFO;  
```  
  
```csharp  
public struct EXCEPTION_INFO {   
   public IDebugProgram2 pProgram;  
   public string         bstrProgramName;  
   public string         bstrExceptionName;  
   public uint           dwCode;  
   public uint           dwState;  
   public Guid           guidType;  
};  
```  
  
## <a name="members"></a>成员  
 pProgram  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)对象，表示发生了异常的程序。  
  
 bstrProgramName  
 发生了异常的程序的名称。  
  
 bstrExceptionName  
 异常的名称。  
  
 dwCode  
 异常或运行时错误标识代码。  
  
 dwState  
 中的值[EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md)枚举，用于定义异常的状态。  
  
 guidType  
 GUID 的语言标识符，即`guidLang`或`guidEng`。  
  
## <a name="remarks"></a>备注  
 此结构作为参数传递给[SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)并[RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)方法。 此结构还传递给[GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)要填充的方法。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [EXCEPTION_STATE](../../../extensibility/debugger/reference/exception-state.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)   
 [RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)   
 [GetException](../../../extensibility/debugger/reference/idebugexceptionevent2-getexception.md)