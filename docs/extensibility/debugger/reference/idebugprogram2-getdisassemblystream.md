---
title: IDebugProgram2::GetDisassemblyStream |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::GetDisassemblyStream
helpviewer_keywords:
- IDebugProgram2::GetDisassemblyStream
ms.assetid: beda0da5-267e-4bf3-96c4-b659d29e2254
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9a80dd1a97be20f6065f6a9e1444dececfa52141
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54975656"
---
# <a name="idebugprogram2getdisassemblystream"></a>IDebugProgram2::GetDisassemblyStream
获取此程序或此计划的一部分的反汇编流。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetDisassemblyStream(   
   DISASSEMBLY_STREAM_SCOPE   dwScope,  
   IDebugCodeContext2*        pCodeContext,  
   IDebugDisassemblyStream2** ppDisassemblyStream  
);  
```  
  
```csharp  
int GetDisassemblyStream(   
   enum_DISASSEMBLY_STREAM_SCOPE  dwScope,  
   IDebugCodeContext2             pCodeContext,  
   out IDebugDisassemblyStream2   ppDisassemblyStream  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwScope`  
 [in]指定一个介于[DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md)定义反汇编流的范围的枚举。  
  
 `pCodeContext`  
 [in][IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)对象，表示从何处着手反汇编流的位置。  
  
 `ppDisassemblyStream`  
 [out]返回[IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)对象，表示反汇编流。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。 返回`E_DISASM_NOTSUPPORTED`如果对于此特定的体系结构不支持反汇编。  
  
## <a name="remarks"></a>备注  
 如果`dwScopes`参数具有`DSS_HUGE`标记[DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md)枚举设置，则应反汇编对整个文件返回大量的反汇编指令或模块。 如果`DSS_HUGE`未设置标志，则应反汇编限于一个小的区域，通常的单个函数。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [DISASSEMBLY_STREAM_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)