---
title: 工作流设计器-TransactionScope 活动设计器
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.TransactionScope.UI
ms.assetid: 8d7ebfc6-7478-4888-b3b0-b14f296096af
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 67c8a5c610492f298d3f2ef6de35444c96f7310f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="transactionscope-activity-designer"></a>TransactionScope 活动设计器

**TransactionScope**活动设计器用于创建和配置<xref:System.Activities.Statements.TransactionScope>活动。

## <a name="the-transactionscope-activity"></a>TransactionScope 活动
 <xref:System.Activities.Statements.TransactionScope> 活动在单个事务中执行所包含的活动。 在 <xref:System.Activities.Statements.TransactionScope.Body%2A> 活动以及该事务中的所有其他参与者成功完成时将提交该事务。

### <a name="using-the-transactionscope-activity-designer"></a>使用 TransactionScope 活动设计器
 **TransactionScope**在找不到活动设计器**事务**类别**工具箱**，通过单击访问的哪一**工具箱**工作流设计器选项卡 (或者，选择**工具栏**从**视图**菜单或 CTRL + ALT + X。)

 **TransactionScope**活动设计器可以拖动从**工具箱**和放置到工作流设计器图面，只要通常放置活动的如内<xref:System.Activities.Statements.Sequence>。 这将创建具有 TransactionScope 的默认 <xref:System.Activities.Statements.TransactionScope> 的 <xref:System.Activities.Activity.DisplayName%2A> 活动。 <xref:System.Activities.Activity.DisplayName%2A>可以在的标头中编辑值**TransactionScope**活动设计器中或在**DisplayName**属性网格的框。

### <a name="the-transactionscope-properties"></a>TransactionScope 属性
 下表列出 <xref:System.Activities.Statements.TransactionScope> 属性并说明如何在设计器中使用它们。 <xref:System.Activities.Activity.DisplayName%2A>和<xref:System.Activities.Statements.TransactionScope.Body%2A>属性可以在工作流设计器图面上编辑。 但其他属性必须在属性网格上编辑。

|属性名|必需|用法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.TransactionScope> 活动的可选友好名称。 默认值为 TransactionScope。 虽然 <xref:System.Activities.Activity.DisplayName%2A> 值不是绝对必需的，但最好使用该属性值。|
|<xref:System.Activities.Statements.TransactionScope.Body%2A>|True|指定要在单个事务中执行的活动。 若要添加<xref:System.Activities.Statements.TransactionScope.Body%2A>活动，将活动从**工具箱**到**正文**框**TransactionScope**带提示文本"放置活动的活动设计器在此处"。|
|<xref:System.Activities.Statements.TransactionScope.IsolationLevel%2A>|True|指定此 <xref:System.Transactions.IsolationLevel> 的 <xref:System.Activities.Statements.TransactionScope>。|
|<xref:System.Activities.Statements.TransactionScope.Timeout%2A>|False|指定必须在其间完成事务的时间间隔（格式为 00:00:00，表示小时:分钟:秒）。 默认值为 1 分钟 (00:01:00)。|
|[System.Activities.Statements.TransactionScope.AbortInstanceOnTransactionFailure](https://msdn.microsoft.com/library/system.activities.statements.transactionscope.abortinstanceontransactionfailure.aspx)|True|指定指示在事务中止的情况下是否应中止工作流的值。|

## <a name="see-also"></a>请参阅

- [事务](../workflow-designer/transaction-activity-designers.md)
- [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [补偿](../workflow-designer/compensate-activity-designer.md)
- [确认](../workflow-designer/confirm-activity-designer.md)