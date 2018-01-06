---
title: "GetScheduledTasksForDebugger 方法 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1c27bd57684fc0a4de0bf56bcc8db9a5561f7d1f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger 方法
检索所有计划任务的数组。  
  
 **Namespace:**<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **程序集：** mscorlib （mscorlib.dll) 中  
  
 由于无法访问此内部成员在.NET Framework 中，以下语法提供共同点中间语言 (CIL)。  
  
## <a name="syntax"></a>语法  
  
```  
.method assembly hidebysig instance class System.Threading.Tasks.Task[] GetScheduledTasksForDebugger() cil managed  
```  
  
## <a name="return-value"></a>返回值  
 所有计划任务的数组。 每个任务执行或已完成执行。  
  
## <a name="remarks"></a>备注  
 此方法不是线程安全，不应与其他实例的同时使用<xref:System.Threading.Tasks.TaskScheduler>它应从调用调试器仅在调试器已挂起所有其他线程时。  
  
## <a name="see-also"></a>请参阅  
 [Taskscheduler 计划的类](../../extensibility/debugger/taskscheduler-class-internal-members.md)