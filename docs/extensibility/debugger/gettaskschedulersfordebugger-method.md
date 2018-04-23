---
title: GetTaskSchedulersForDebugger 方法 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- GetTaskSchedulersForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 58aa236a-5ab8-4695-b303-89dffdbcd946
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d5d0b78a4f115d1ba07848db914289c35034d465
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="gettaskschedulersfordebugger-method"></a>GetTaskSchedulersForDebugger 方法
检索的所有数组<xref:System.Threading.Tasks.TaskScheduler>当前处于活动状态的对象。  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **程序集：** mscorlib （mscorlib.dll) 中  
  
 由于无法访问此内部成员在.NET Framework 中，以下语法提供共同点中间语言 (CIL)。  
  
## <a name="syntax"></a>语法  
  
```  
.method assembly hidebysig static class System.Threading.Tasks.TaskScheduler[] GetTaskSchedulersForDebugger() cil managed  
```  
  
## <a name="return-value"></a>返回值  
 数组的所有<xref:System.Threading.Tasks.TaskScheduler>中当前处于活动状态的对象<xref:System.AppDomain>。  
  
## <a name="remarks"></a>备注  
 此方法不是线程安全，不应与其他实例的同时使用<xref:System.Threading.Tasks.TaskScheduler>。 它应从调用调试器仅在调试器已挂起所有其他线程时。  
  
## <a name="see-also"></a>另请参阅  
 [Taskscheduler 计划的类](../../extensibility/debugger/taskscheduler-class-internal-members.md)