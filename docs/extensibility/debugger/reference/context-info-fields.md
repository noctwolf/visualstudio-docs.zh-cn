---
title: CONTEXT_INFO_FIELDS |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- CONTEXT_INFO_FIELDS
helpviewer_keywords:
- CONTEXT_INFO_FIELDS enumeration
ms.assetid: ef436bd3-738e-47e8-828c-8febce752439
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 05616ba660af188c26f192b97e29d5b60e04fe8a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="contextinfofields"></a>CONTEXT_INFO_FIELDS
指定要检索有关内存上下文的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_CONTEXT_INFO_FIELDS {   
   CIF_MODULEURL =       0x00000001,  
   CIF_FUNCTION =        0x00000002,  
   CIF_FUNCTIONOFFSET =  0x00000004,  
   CIF_ADDRESS =         0x00000008,  
   CIF_ADDRESSOFFSET =   0x00000010,  
   CIF_ADDRESSABSOLUTE = 0x00000020,  
   CIF_ALLFIELDS =       0x0000003f  
};  
typedef DWORD CONTEXT_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_CONTEXT_INFO_FIELDS {  
   CIF_MODULEURL =       0x00000001,  
   CIF_FUNCTION =        0x00000002,  
   CIF_FUNCTIONOFFSET =  0x00000004,  
   CIF_ADDRESS =         0x00000008,  
   CIF_ADDRESSOFFSET =   0x00000010,  
   CIF_ADDRESSABSOLUTE = 0x00000020,  
   CIF_ALLFIELDS =       0x0000003f  
};  
```  
  
## <a name="members"></a>成员  
 CIF_MODULEURL  
 初始化/使用`bstrModuleUrl`字段[CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)结构。  
  
 CIF_FUNCTION  
 初始化/使用`bstrFunction`字段`CONTEXT_INFO`结构。  
  
 CIF_FUNCTIONOFFSET  
 初始化/使用`posFunctionOffset`字段`CONTEXT_INFO`结构。  
  
 CIF_ADDRESS  
 初始化/使用`bstrAddress`字段`CONTEXT_INFO`结构。  
  
 CIF_ADDRESSOFFSET  
 初始化/使用`bstrAddressOffset`字段`CONTEXT_INFO`结构。  
  
 CIF_ALLFIELDS  
 初始化/使用的所有字段`CONTEXT_INFO`结构。  
  
## <a name="remarks"></a>备注  
 这些值传递到参数[GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)方法，以指示哪些字段[CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)结构是否被初始化。  
  
 这些标志也用于指示哪些字段`CONTEXT_INFO`结构均使用和有效时返回的结构。  
  
 可能与按位 OR 组合这些值。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)