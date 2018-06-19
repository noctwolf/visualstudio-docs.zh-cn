---
title: Taskscheduler 计划的类的内部成员 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- TaskScheduler class [.NET Framework debug engines]
- debug engines, TaskScheduler class [.NET Framework]
ms.assetid: 87f1c969-0217-4464-8907-7609c1bf61d3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 18cd3ec809df921d6baefbf8018fefc77db238d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126748"
---
# <a name="taskscheduler-class---internal-members"></a>Taskscheduler 计划的类的内部成员
本主题介绍的内部成员<xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>帮助你的类实现自定义调试器。 有关此类的常规信息，请参阅<xref:System.Threading.Tasks.TaskScheduler>参考主题。  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **程序集：** mscorlib （mscorlib.dll) 中  
  
 由于无法访问这些内部成员在.NET Framework 中，以下语法提供共同点中间语言 (CIL)。  
  
## <a name="syntax"></a>语法  
  
```  
.class public abstract auto ansi beforefieldinit System.Threading.Tasks.TaskScheduler  
       extends System.Object  
```  
  
## <a name="members"></a>成员  
  
### <a name="methods"></a>方法  
  
|名称|描述|  
|----------|-----------------|  
|[GetScheduledTasksForDebugger](../../extensibility/debugger/getscheduledtasksfordebugger-method.md)|检索所有计划任务的数组。|  
|[GetTaskSchedulersForDebugger](../../extensibility/debugger/gettaskschedulersfordebugger-method.md)|检索的所有数组<xref:System.Threading.Tasks.TaskScheduler>当前处于活动状态的对象。|  
  
## <a name="remarks"></a>备注  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [.NET Framework 的并行扩展内幕](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)