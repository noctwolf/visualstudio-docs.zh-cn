---
title: 工作流设计器的旧工作流活动
ms.date: 01/18/2017
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, activities
- activities
- workflow activities
ms.assetid: 4af7a06b-1e82-43c8-aec8-0dc5fb63d08a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 45c24c0be518e58ce87af11a38486818ca4a3ac7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31979472"
---
# <a name="legacy-workflow-activities"></a>旧版工作流活动

Windows Workflow Foundation (WF) 包括一组默认的活动，以提供功能控制流、 条件、 事件处理、 状态管理和通信的应用程序和服务。 在设计工作流，你可以使用系统提供的活动提供的 Windows 工作流设计器中，或者可以创建自己的自定义活动。

下表列出了 Windows Workflow Foundation 框架现成可用的活动集。 许多，但并非所有这些活动的由表示活动设计器可以从访问**工具箱**的工作流设计器。 若要创建活动，将其设计器从**工具箱**并将其放在设计图面上。

|活动|描述|
|--------------|-----------------|
|<xref:System.Workflow.Activities.CallExternalMethodActivity>|与使用**HandleExternalEventActivity**与本地服务的输入和输出通信的活动。 有关详细信息，请参阅[使用 CallExternalMethodActivity 活动](http://go.microsoft.com/fwlink?LinkID=65060)。|
|**System.Workflow.Activities.CancellationHandlerActivity**|用于包含在所有复合活动的子项完成执行之前所取消复合活动的清理逻辑。 有关详细信息，请参阅[使用 CancellationHandlerActivity 活动](http://go.microsoft.com/fwlink?LinkID=65061)。|
|<xref:System.Workflow.Activities.CodeActivity>|使你能够向工作流中添加 Visual Basic 或 C# 代码。 有关详细信息，请参阅[使用 CodeActivity 活动](http://go.microsoft.com/fwlink?LinkID=65062)。|
|<xref:System.Workflow.Activities.CompensatableSequenceActivity>|<xref:System.Workflow.Activities.SequenceActivity> 的可补偿版本。 有关详细信息，请参阅[使用 CompensatableSequenceActivity 活动](http://go.microsoft.com/fwlink?LinkID=65002)。|
|**System.Workflow.Activities.CompensatableTransactionScopeActivity**|可补偿版本**TransactionScopeActivity**。 有关详细信息，请参阅[使用 CompensatableTransactionScopeActivity 活动](http://go.microsoft.com/fwlink?LinkID=65063)。|
|**System.Workflow.Activities.CompensateActivity**|使你能够调用代码来撤消或补偿发生错误时已由工作流执行的操作。 有关详细信息，请参阅[使用 CompensateActivity 活动](http://go.microsoft.com/fwlink?LinkID=65064)。|
|**System.Workflow.Activities.CompensationHandlerActivity**|有关详细信息，执行已完成的 TransactionScopeActivity 活动的补偿的一个或多个活动的包装请参阅[使用 CompensationHandlerActivity 活动](http://go.microsoft.com/fwlink?LinkID=65065)。|
|<xref:System.Workflow.Activities.ConditionedActivityGroup>|根据应用于 <xref:System.Workflow.Activities.ConditionedActivityGroup> 活动本身的条件以及分别应用于每个子活动的条件来执行子活动。 有关详细信息，请参阅[使用 ConditionedActivityGroup 活动](http://go.microsoft.com/fwlink?LinkID=65066)。|
|<xref:System.Workflow.Activities.DelayActivity>|使您能够在工作流中建立基于超时间隔的延迟。 有关详细信息，请参阅[使用 DelayActivity 活动](http://go.microsoft.com/fwlink?LinkID=65067)。|
|<xref:System.Workflow.Activities.EventDrivenActivity>|包装在指定事件发生时执行的一个或多个活动。 有关详细信息，请参阅[使用 EventDrivenActivity 活动](http://go.microsoft.com/fwlink?LinkID=65068)。|
|<xref:System.Workflow.Activities.EventHandlersActivity>|提供一个用于将事件与活动关联的框架。 有关详细信息，请参阅[使用 EventHandlersActivity 活动](http://go.microsoft.com/fwlink?LinkID=65069)。|
|<xref:System.Workflow.Activities.EventHandlingScopeActivity>|执行同时使用其主要子活动<xref:System.Workflow.Activities.EventHandlersActivity>。 有关详细信息，请参阅[使用 EventHandlingScopeActivity 活动](http://go.microsoft.com/fwlink?LinkID=65070)。|
|**System.Workflow.Activities.FaultHandlerActivity**|用于处理指定类型的异常。 有关详细信息，请参阅[使用 FaultHandlerActivity 活动](http://go.microsoft.com/fwlink?LinkID=65071)。|
|**System.Workflow.Activities.FaultHandlersActivity**|表示类型的子活动的有序的列表有一个复合活动**System.Workflow.Activities.FaultHandlerActivity**。 有关详细信息，请参阅[使用 FaultHandlersActivity 活动](http://go.microsoft.com/fwlink?LinkID=65072)。|
|<xref:System.Workflow.Activities.HandleExternalEventActivity>|结合使用<xref:System.Workflow.Activities.CallExternalMethodActivity>与本地服务的输入和输出通信的活动。 有关详细信息，请参阅[使用 HandleExternalEventActivity 活动](http://go.microsoft.com/fwlink?LinkID=65073)。|
|<xref:System.Workflow.Activities.IfElseActivity>|测试每个分支上的条件并为其条件为第一个分支上执行活动**true**。 有关详细信息，请参阅[使用 IfElseActivity 活动](http://go.microsoft.com/fwlink?LinkID=65074)。|
|<xref:System.Workflow.Activities.IfElseBranchActivity>|表示 <xref:System.Workflow.Activities.IfElseActivity> 的分支。 有关详细信息，请参阅[使用 IfElseBranchActivity 活动](http://go.microsoft.com/fwlink?LinkID=65075)。|
|<xref:System.Workflow.Activities.InvokeWebServiceActivity>|使工作流能够调用 Web 服务。 有关详细信息，请参阅[使用 InvokeWebServiceActivity 活动](http://go.microsoft.com/fwlink?LinkID=65076)。|
|<xref:System.Workflow.Activities.InvokeWorkflowActivity>|使工作流能够调用其他工作流。 有关详细信息，请参阅[使用 InvokeWorkflowActivity 活动](http://go.microsoft.com/fwlink?LinkID=65077)。|
|<xref:System.Workflow.Activities.ListenActivity>|只包含 <xref:System.Workflow.Activities.EventDrivenActivity> 子活动的复合活动。 有关详细信息，请参阅[使用 ListenActivity 活动](http://go.microsoft.com/fwlink?LinkID=65078)。|
|<xref:System.Workflow.Activities.ParallelActivity>|提供一种方法来计划两个或更多子**SequenceActivity**同时处理的活动分支。 有关详细信息，请参阅[使用 ParallelActivity 活动](http://go.microsoft.com/fwlink?LinkID=65079)。|
|<xref:System.Workflow.Activities.PolicyActivity>|用于表示规则的集合。 规则由条件和引起的操作组成。 有关详细信息，请参阅[使用 PolicyActivity 活动](http://go.microsoft.com/fwlink?LinkID=65004)。|
|<xref:System.Workflow.Activities.ReplicatorActivity>|创建单个子活动的多个实例。 有关详细信息，请参阅[使用 ReplicatorActivity 活动](http://go.microsoft.com/fwlink?LinkID=65080)。|
|<xref:System.Workflow.Activities.SequenceActivity>|提供了一种简单的方法，可将多个活动链接在一起以按顺序执行。 有关详细信息，请参阅[使用 SequenceActivity 活动](http://go.microsoft.com/fwlink?LinkID=65081)。|
|<xref:System.Workflow.Activities.SetStateActivity>|指定到新状态的转换。 有关详细信息，请参阅[使用 SetStateActivity 活动](http://go.microsoft.com/fwlink?LinkID=65082)。|
|<xref:System.Workflow.Activities.StateActivity>|表示状态机工作流中的一个状态。 有关详细信息，请参阅[使用 StateActivity 活动](http://go.microsoft.com/fwlink?LinkID=65083)。|
|<xref:System.Workflow.Activities.StateFinalizationActivity>|在中使用<xref:System.Workflow.Activities.StateActivity>作为离开时执行的子活动的容器活动**StateActivity**活动。 有关详细信息，请参阅[使用 StateFinalizationActivity 活动](http://go.microsoft.com/fwlink?LinkID=65008)。|
|<xref:System.Workflow.Activities.StateInitializationActivity>|在中使用<xref:System.Workflow.Activities.StateActivity>作为输入时执行的子活动的容器活动**StateActivity**活动。 有关详细信息，请参阅[使用 StateInitializationActivity 活动](http://go.microsoft.com/fwlink?LinkID=65006)。|
|**System.Workflow.Activities.SuspendActivity**|挂起工作流的操作，以便能够在出现某种需要特别注意的错误情况时进行干预。 有关详细信息，请参阅[使用 SuspendActivity 活动](http://go.microsoft.com/fwlink?LinkID=65084)。|
|**System.Workflow.Activities.SynchronizationScopeActivity**|在同步的域中按顺序执行所包含的活动。 有关详细信息，请参阅[使用 SynchronizationScopeActivity 活动](http://go.microsoft.com/fwlink?LinkID=65085)。|
|**System.Workflow.Activities.TerminateActivity**|使您能够在发生错误情形时立即结束工作流的操作。 有关详细信息，请参阅[使用 TerminateActivity 活动](http://go.microsoft.com/fwlink?LinkID=65086)。|
|**System.Workflow.Activities.ThrowActivity**|使您能够捕获作为工作流过程元数据一部分引发的业务异常。 有关详细信息，请参阅[使用 ThrowActivity 活动](http://go.microsoft.com/fwlink?LinkID=65087)。|
|**System.Workflow.Activities.TransactionScopeActivity**|提供一个用于事务和异常处理的框架。 有关详细信息，请参阅[使用 TransactionScopeActivity 活动](http://go.microsoft.com/fwlink?LinkID=65088)。|
|<xref:System.Workflow.Activities.WebServiceFaultActivity>|使你能够建立所出现 Web 服务错误的模型。 有关详细信息，请参阅[使用 WebServiceFaultActivity 活动](http://go.microsoft.com/fwlink?LinkID=65089)。|
|<xref:System.Workflow.Activities.WebServiceInputActivity>|接收来自 Web 服务的数据。 有关详细信息，请参阅[使用 WebServiceInputActivity 活动](http://go.microsoft.com/fwlink?LinkID=65090)。|
|<xref:System.Workflow.Activities.WebServiceOutputActivity>|对工作流发出的 Web 服务请求做出响应。 有关详细信息，请参阅[使用 WebServiceOutputActivity 活动](http://go.microsoft.com/fwlink?LinkID=65092)。|
|<xref:System.Workflow.Activities.WhileActivity>|使工作流能够在条件得到满足之前进行循环。 有关详细信息，请参阅[使用 WhileActivity 活动](http://go.microsoft.com/fwlink?LinkID=65091)。|

有关如何创建自定义活动的详细信息，请参阅[开发自定义活动](http://go.microsoft.com/fwlink?LinkID=65023)和[使用旧版活动设计器](../workflow-designer/using-the-legacy-activity-designer.md)。

## <a name="see-also"></a>请参阅

- [Windows Workflow Foundation 活动](http://go.microsoft.com/fwlink?LinkID=65005)
- [开发工作流](http://go.microsoft.com/fwlink?LinkID=65010)
- [开发工作流活动](http://go.microsoft.com/fwlink?LinkID=65023)