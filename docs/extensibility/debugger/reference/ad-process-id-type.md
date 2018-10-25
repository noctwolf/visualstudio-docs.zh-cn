---
title: AD_PROCESS_ID_TYPE |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: 1fa934610778479551d411a4b231a4b190f29bcd
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49937403"
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
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)