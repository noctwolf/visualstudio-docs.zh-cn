---
title: PROCESS_INFO_FLAGS |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- PROCESS_INFO_FLAGS
helpviewer_keywords:
- PROCESS_INFO_FLAGS enumeration
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 04bc34de6e7ecbc438cfc63ed08c684cf4224366
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49917019"
---
# <a name="processinfoflags"></a>PROCESS_INFO_FLAGS

描述或指定进程的属性。

## <a name="syntax"></a>语法

```cpp
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
指示由调试器调试该进程。 可能会[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]调试器，也可能是一些其他调试器，例如，WinDbg。

PIFLAG_PROCESS_STOPPED  
指示该进程已停止。 有效才`PIFLAG_DEBUGGER_ATTACHED`还指定了。 可在 Visual Studio 2005 和更高版本。

PIFLAG_PROCESS_RUNNING  
指示进程正在运行。 有效才`PIFLAG_DEBUGGER_ATTACHED`还指定了。 可在 Visual Studio 2005 和更高版本。

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