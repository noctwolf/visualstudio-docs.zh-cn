---
title: PROCESS_INFO_FLAGS |Microsoft 文档
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
ms.openlocfilehash: 91e4c4648108cdc6afa28f5a5dd8f9bfd46fcf59
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="processinfoflags"></a>PROCESS_INFO_FLAGS

本文介绍或指定的进程属性。

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
指示进程是一个系统进程。

PIFLAG_DEBUGGER_ATTACHED  
指示由调试器调试该进程。 它可能是[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]可能某些其他调试器，例如，WinDbg 调试器，或它。

PIFLAG_PROCESS_STOPPED  
指示该进程已停止。 有效才`PIFLAG_DEBUGGER_ATTACHED`还指定。 在 Visual Studio 2005 和更高版本可用。

PIFLAG_PROCESS_RUNNING  
指示进程正在运行。 有效才`PIFLAG_DEBUGGER_ATTACHED`还指定。 在 Visual Studio 2005 和更高版本可用。

## <a name="remarks"></a>备注

用于`Flags`的成员[PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)结构。

这些标志可以与按位组合`OR`。

## <a name="requirements"></a>要求

标头： msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>另请参阅

[枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)