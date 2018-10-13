---
title: PROCESS_INFO_FLAGS |Microsoft Docs
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
- PROCESS_INFO_FLAGS
helpviewer_keywords:
- PROCESS_INFO_FLAGS enumeration
ms.assetid: 696951ce-701a-40c2-ac8c-b897f3aae6e2
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 03eb17934620a1ec8bf23d28519d5615fab62ef6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49298306"
---
# <a name="processinfoflags"></a>PROCESS_INFO_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

描述或指定进程的属性。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
enum enum_PROCESS_INFO_FLAGS {   
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,  
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,  
   PIFLAG_PROCESS_STOPPED   = 0x00000004,  
   PIFLAG_PROCESS_RUNNING   = 0x00000008,  
};  
typedef DWORD PROCESS_INFO_FLAGS;  
```  
  
```csharp  
enum enum_PROCESS_INFO_FLAGS {   
   PIFLAG_SYSTEM_PROCESS    = 0x00000001,  
   PIFLAG_DEBUGGER_ATTACHED = 0x00000002,  
   PIFLAG_PROCESS_STOPPED   = 0x00000004,  
   PIFLAG_PROCESS_RUNNING   = 0x00000008,  
};  
```  
  
## <a name="members"></a>成员  
 PIFLAG_SYSTEM_PROCESS  
 指示该过程是一个系统进程。  
  
 PIFLAG_DEBUGGER_ATTACHED  
 指示由调试器调试该进程。 可能会[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]调试器，也可能是一些其他调试器，例如，WinDbg。  
  
 PIFLAG_PROCESS_STOPPED  
 指示该进程已停止。 有效才`PIFLAG_DEBUGGER_ATTACHED`还指定了。 中提供[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]及更高版本。  
  
 PIFLAG_PROCESS_RUNNING  
 指示进程正在运行。 有效才`PIFLAG_DEBUGGER_ATTACHED`还指定了。 中提供[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]及更高版本。  
  
## <a name="remarks"></a>备注  
 用于`Flags`的成员[PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)结构。  
  
 可能的按位组合这些标志`OR`。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)

