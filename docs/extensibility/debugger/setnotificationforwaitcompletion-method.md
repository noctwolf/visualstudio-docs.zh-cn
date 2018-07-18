---
title: SetNotificationForWaitCompletion 方法 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- SetNotificationForWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: da149c9a-20f4-4543-a29e-429c8c1d2e19
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a005ee7d624604dd716042bd839b48b7a367dd48
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127013"
---
# <a name="setnotificationforwaitcompletion-method"></a>SetNotificationForWaitCompletion 方法
设置或清除 TASK_STATE_WAIT_COMPLETION_NOTIFICATION 状态位。  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **程序集：** mscorlib （mscorlib.dll) 中  
  
## <a name="syntax"></a>语法  
  
```vb  
internal void SetNotificationForWaitCompletion(bool enabled)  
```  
  
#### <a name="parameters"></a>参数  
 `enabled`  
  
 `true` 若要设置的位;`false`到取消设置位。  
  
## <a name="exceptions"></a>异常  
  
## <a name="remarks"></a>备注  
 调试器将设置此位，以帮助单步从异步方法正文。 如果`enabled`是`true`，必须调用此方法仅在尚未完成的任务上。 如果`enabled`是`false`，不能对已完成的任务调用此方法。 在既情况下，它应仅用于承诺样式任务。  
  
## <a name="requirements"></a>要求  
  
## <a name="see-also"></a>另请参阅  
 [任务类](../../extensibility/debugger/task-class-internal-members.md)