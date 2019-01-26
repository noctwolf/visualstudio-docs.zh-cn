---
title: PROVIDER_FIELDS | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- PROVIDER_FIELDS
helpviewer_keywords:
- PROVIDER_FIELDS enumeration
ms.assetid: 39631545-2b0e-45b4-978b-d63656484b02
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ec381484a0628715f593dad10848f6e8f4206eee
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "55071015"
---
# <a name="providerfields"></a>PROVIDER_FIELDS
指定与程序提供程序关联的属性。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_PROVIDER_FIELDS {  
   PFIELD_PROGRAM_NODES       = 0x01,  
   PFIELD_IS_DEBUGGER_PRESENT = 0x02  
};  
typedef DWORD PROVIDER_FIELDS;  
```  
  
```csharp  
public enum enum_PROVIDER_FIELDS {  
   PFIELD_PROGRAM_NODES       = 0x01,  
   PFIELD_IS_DEBUGGER_PRESENT = 0x02  
};  
```  
  
## <a name="members"></a>成员  
 PFIELD_PROGRAM_NODES  
 `ProgramNodes`字段才有效。  
  
 PFIELD_IS_DEBUGGER_PRESENT  
 `fIsDebuggerPresent`字段才有效。  
  
## <a name="remarks"></a>备注  
 这些值中返回`Fields`的成员[PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md)结构，以指示已显式填充结构的哪些字段。  
  
 可以组合这些值的按位`OR`。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md)