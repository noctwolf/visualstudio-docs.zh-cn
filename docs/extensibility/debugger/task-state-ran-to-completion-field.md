---
title: TASK_STATE_RAN_TO_COMPLETION 字段 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- TASK_STATE_RAN_TO_COMPLETION field, Task class [.NET Framework debug engines]
ms.assetid: 0f4830af-fe0c-4141-b768-817f4e426b8c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a2bfec03e44b4af46ed75761d96f1e37bc1370e0
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56704899"
---
# <a name="taskstaterantocompletion-field"></a>TASK_STATE_RAN_TO_COMPLETION 字段
已成功完成执行的任务。

 **Namespace**：<xref:System.Threading.Tasks?displayProperty=fullName>

 **程序集：** mscorlib (在*mscorlib.dll*)

 无法从.NET Framework 来访问此内部成员，因为以下语法提供通用中间语言 (CIL)。

## <a name="syntax"></a>语法

```csharp
.field static assembly literal int32 TASK_STATE_RAN_TO_COMPLETION = int32(0x02000000)
```

## <a name="remarks"></a>备注
 如果[m_stateFlags](../../extensibility/debugger/m-stateflags-field.md)字段包含此值，<xref:System.Threading.Tasks.Task.Status%2A>属性返回<xref:System.Threading.Tasks.TaskStatus?displayProperty=fullName>。

## <a name="see-also"></a>请参阅
- [Task 类](../../extensibility/debugger/task-class-internal-members.md)