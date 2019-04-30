---
title: GetScheduledTasksForDebugger 方法 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 221a1b49bd3083e0d2dd0248cdf182d699423057
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62889926"
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger 方法
检索所有计划任务的数组。

 **Namespace**：<xref:System.Threading.Tasks?displayProperty=fullName>

 **程序集：** mscorlib (在*mscorlib.dll*)

 无法从.NET Framework 来访问此内部成员，因为以下语法提供通用中间语言 (CIL)。

## <a name="syntax"></a>语法

```csharp
.method assembly hidebysig instance class System.Threading.Tasks.Task[] GetScheduledTasksForDebugger() cil managed
```

## <a name="return-value"></a>返回值
 所有计划任务的数组。 每个任务正在执行或已完成执行。

## <a name="remarks"></a>备注
 此方法不是线程安全且不应使用它与其他实例同时<xref:System.Threading.Tasks.TaskScheduler>。 仅当在调试器已挂起的所有其他线程时，请从调试器中调用此方法。

## <a name="see-also"></a>请参阅
- [TaskScheduler 类](../../extensibility/debugger/taskscheduler-class-internal-members.md)