---
title: GetTaskSchedulersForDebugger 方法 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetTaskSchedulersForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 58aa236a-5ab8-4695-b303-89dffdbcd946
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d5df6dc3147a92f14d6858a82a6d997442dec30b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925649"
---
# <a name="gettaskschedulersfordebugger-method"></a>GetTaskSchedulersForDebugger 方法
检索的所有数组<xref:System.Threading.Tasks.TaskScheduler>当前处于活动状态的对象。

 **Namespace**：<xref:System.Threading.Tasks?displayProperty=fullName>

 **程序集：** mscorlib (在*mscorlib.dll*)

 无法从.NET Framework 来访问此内部成员，因为以下语法提供通用中间语言 (CIL)。

## <a name="syntax"></a>语法

```csharp
.method assembly hidebysig static class System.Threading.Tasks.TaskScheduler[] GetTaskSchedulersForDebugger() cil managed
```

## <a name="return-value"></a>返回值
 所有的数组<xref:System.Threading.Tasks.TaskScheduler>在此当前处于活动状态的对象<xref:System.AppDomain>。

## <a name="remarks"></a>备注
 此方法不是线程安全且不应使用它与其他实例同时<xref:System.Threading.Tasks.TaskScheduler>。 仅当在调试器已挂起的所有其他线程时，请从调试器中调用此方法。

## <a name="see-also"></a>请参阅
- [TaskScheduler 类](../../extensibility/debugger/taskscheduler-class-internal-members.md)