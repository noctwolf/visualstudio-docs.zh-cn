---
title: .NET framework 并行扩展内幕 |Microsoft Docs
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
- debug engines, internals [.NET Framework]
ms.assetid: 93e07cfa-91fa-464c-b866-8bf5570411df
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8c6a6c0444da1200e5cd28a0a4c97a74587acefa
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49239955"
---
# <a name="parallel-extension-internals-for-the-net-framework"></a>.NET Framework 的并行扩展内幕
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本节介绍了内部类型、 方法和字段的类，可帮助您实现自定义.NET Framework 并行扩展调试器。  
  
## <a name="in-this-section"></a>本节内容  
 [Task 类](../../extensibility/debugger/task-class-internal-members.md)  
 内部数据成员进行了说明<xref:System.Threading.Tasks.Task?displayProperty=fullName>类。  
  
 [TaskScheduler 类](../../extensibility/debugger/taskscheduler-class-internal-members.md)  
 内部数据成员进行了说明<xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>类。  
  
 [ContingentProperties 类](../../extensibility/debugger/contingentproperties-class-internal-members.md)  
 内部数据成员进行了说明`System.Threading.Tasks.ContingentProperties`类。  
  
 [AsyncTaskMethodBuilder 结构](../../extensibility/debugger/asynctaskmethodbuilder-structure-internal-members.md)  
 介绍的内部成员<xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder>结构。  
  
 [AsyncTaskMethodBuilder\<TResult > 结构](../../extensibility/debugger/asynctaskmethodbuilder-tresult-structure-internal-members.md)  
 介绍的内部成员<xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601>结构。  
  
 [AsyncVoidMethodBuilder 结构](../../extensibility/debugger/asyncvoidmethodbuilder-structure-internal-members.md)  
 介绍的内部成员<xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder>结构。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [Visual Studio 调试器可扩展性](../../extensibility/debugger/visual-studio-debugger-extensibility.md)   
 [并行编程](http://msdn.microsoft.com/library/4d83c690-ad2d-489e-a2e0-b85b898a672d)

