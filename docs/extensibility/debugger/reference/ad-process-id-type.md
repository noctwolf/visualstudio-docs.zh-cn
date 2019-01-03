---
title: AD_PROCESS_ID_TYPE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- AD_PROCESS_ID_TYPE
helpviewer_keywords:
- AD_PROCESS_ID_TYPE enumeration
ms.assetid: 0aab80e9-285a-4697-94ac-c864d42a6aaa
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f27791b555d2f18e1e0a338bbfb5893f9047fd4e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53819583"
---
# <a name="adprocessidtype"></a>AD_PROCESS_ID_TYPE
指定如何解释中的进程 ID [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)结构。  
  
## <a name="syntax"></a>语法  
  
```cpp  
enum enum_AD_PROCESS_ID {  
   AD_PROCESS_ID_SYSTEM = 0,  
   AD_PROCESS_ID_GUID   = 1  
};  
typedef DWORD AD_PROCESS_ID_TYPE;  
```  
  
```csharp  
public enum enum_AD_PROCESS_ID {  
   AD_PROCESS_ID_SYSTEM = 0,  
   AD_PROCESS_ID_GUID   = 1  
};  
```  
  
## <a name="members"></a>成员  
 AD_PROCESS_ID_SYSTEM  
 进程 ID 是系统标识符。 使用`ProcessId.dwProcessId`字段[AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)结构。  
  
 AD_PROCESS_ID_GUID  
 进程 ID 是一个 GUID。 使用`ProcessId.guidProcessId`字段的`AD_PROCESS_ID`结构。  
  
## <a name="remarks"></a>备注  
 用于`ProcessIdType`的成员[AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)结构以确定结构中包含的进程 ID 的类型。 确定如何解释`ProcessId`联合结构中。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 命名空间:Microsoft.VisualStudio.Debugger.Interop  
  
 程序集：Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)