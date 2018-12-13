---
title: EXCEPTION_INFO |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- EXCEPTION_INFO
helpviewer_keywords:
- EXCEPTION_INFO structure
ms.assetid: d046957a-b97d-420b-b46b-c67cbaef709e
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8a6feebb3be6f6f6f50a7d1a2ed3ff8525dacf6c
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51786881"
---
# <a name="exceptioninfo"></a>EXCEPTION_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

描述异常或引发由正在调试的程序的运行时错误。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
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

