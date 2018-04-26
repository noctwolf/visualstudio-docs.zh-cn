---
title: 工作流设计器-Compensate 活动设计器
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Compensate.UI
ms.assetid: 7347c947-bfff-4bad-becd-5cd23e7b24cd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8278066a12df0d195770391d0b2f3144ba16487d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="compensate-activity-designer"></a>Compensate 活动设计器

**Compensate**活动设计器用于创建和配置<xref:System.Activities.Statements.Compensate>活动。

## <a name="the-compensate-activity"></a>Compensate 活动
 <xref:System.Activities.Statements.Compensate> 活动为 <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> 中包含的活动显式调用 <xref:System.Activities.Statements.CompensableActivity>。 如果 <xref:System.Activities.Statements.Compensate> 活动未在 <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> 的 <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>、<xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> 或 <xref:System.Activities.Statements.CompensableActivity> 中使用，则必须指定 <xref:System.Activities.Statements.Compensate.Target%2A> 属性。

 由 <xref:System.Activities.Statements.CompensationToken> 指定的 <xref:System.Activities.Statements.Compensate.Target%2A> 提供了在 <xref:System.Activities.Statements.CompensableActivity> 的 <xref:System.Activities.Statements.CompensableActivity.Body%2A> 成功完成之后显式确认或补偿 <xref:System.Activities.Statements.CompensableActivity> 的方法。

### <a name="using-the-compensate-activity-designer"></a>使用 Compensate 活动设计器
 **Compensate**在找不到活动设计器**事务**类别**工具箱**。 若要打开**工具箱**，选择**工具箱**工作流设计器左侧的选项卡 (或者，选择**工具栏**从**视图**菜单上或 CTRL + ALT + X。)

 **Compensate**活动设计器可以拖动从**工具箱**和放置到工作流设计器图面，只要放置活动的如内<xref:System.Activities.Statements.Sequence>。 删除活动设计器创建<xref:System.Activities.Statements.Compensate>默认值的活动<xref:System.Activities.Activity.DisplayName%2A>的补偿。 <xref:System.Activities.Activity.DisplayName%2A>可以在的标头中编辑值**Compensate**活动设计器中或在**DisplayName**属性网格的框。

### <a name="the-compensate-properties"></a>Compensate 属性
 下表列出 <xref:System.Activities.Statements.CancellationScope> 属性并说明如何在设计器中使用它们。 <xref:System.Activities.Activity.DisplayName%2A>属性可以在属性网格中或在工作流设计器图面上编辑。 编辑<xref:System.Activities.Statements.Compensate.Target%2A>在属性网格中的属性。

|属性名|必需|用法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|指定 <xref:System.Activities.Statements.Compensate> 活动的可选友好名称。 默认值为 Compensate。|
|<xref:System.Activities.Statements.Compensate.Target%2A>|True|指定 <xref:System.Activities.InArgument%601>，它包含此 <xref:System.Activities.Statements.CompensationToken> 活动的 <xref:System.Activities.Statements.Compensate>。|

## <a name="see-also"></a>请参阅

- [事务](../workflow-designer/transaction-activity-designers.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [Compensate 活动设计器](../workflow-designer/compensate-activity-designer.md)
- [确认](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)