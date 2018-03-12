---
title: PROCESS_INFO_FLAGS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PROCESS_INFO_FLAGS
helpviewer_keywords:
- PROCESS_INFO_FLAGS enumeration
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 6e95e9f66b804fed102c0d51aa17a1bfe4f51ca5
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
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

## <a name="requirements"></a>惠?

标头： msdbg.h

Namespace: Microsoft.VisualStudio.Debugger.Interop

Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>请参阅

[枚举](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)