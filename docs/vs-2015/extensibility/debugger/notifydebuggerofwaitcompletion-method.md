---
title: NotifyDebuggerOfWaitCompletion 方法 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- NotifyDebuggerOfWaitCompletion method, Task class [.NET Framework debug engines]
ms.assetid: 841c5908-4f3f-400b-a7b0-96a95f362817
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 49a51a09e5566cb92ee13f136341545190525613
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49232669"
---
# <a name="notifydebuggerofwaitcompletion-method"></a>NotifyDebuggerOfWaitCompletion 方法
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

由调试器使用断点目标的占位符方法。 此方法不能内联或优化。  
  
 **Namespace**：<xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **程序集：** mscorlib （在 mscorlib.dll 中)  
  
## <a name="syntax"></a>语法  
  
```vb  
private void NotifyDebuggerOfWaitCompletion()  
```  
  
## <a name="remarks"></a>备注  
 与任务的所有联接操作应都调用此方法，如果其调试器通知位设置。  
  
## <a name="requirements"></a>要求  
  
## <a name="see-also"></a>请参阅  
 [Task 类](../../extensibility/debugger/task-class-internal-members.md)

