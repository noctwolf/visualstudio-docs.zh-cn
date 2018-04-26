---
title: 工作流设计器-CompensableActivity 活动设计器
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.CompensableActivity.UI
ms.assetid: e0340d89-d39e-4a52-8557-13e27040d7b5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fdab42766fd20989831e446a45115d17b3ee28fd
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="compensableactivity-activity-designer"></a>CompensableActivity 活动设计器

**CompensableActivity**活动设计器用于创建和配置<xref:System.Activities.Statements.CompensableActivity>活动。

## <a name="the-compensableactivity-activity"></a>CompensableActivity 活动
 <xref:System.Activities.Statements.CompensableActivity> 定义可在成功完成之后得到确认或补偿的工作单元。

### <a name="using-the-compensableactivity-activity-designer"></a>使用 CompensableActivity 活动设计器
 **CompensableActivity**在找不到活动设计器**事务**类别**工具箱**。 若要打开**工具箱**，选择**工具箱**工作流设计器左侧的选项卡。 或者，选择**工具栏**从**视图**菜单上或按 CTRL + ALT + X。

 **CompensableActivity**活动设计器可以拖动从**工具箱**和放置到工作流设计器图面。 无法删除活动设计器内的<xref:System.Activities.Statements.Sequence>。 删除活动设计器创建<xref:System.Activities.Statements.CompensableActivity>默认值的活动<xref:System.Activities.Activity.DisplayName%2A>的 CompensableActivity。 编辑<xref:System.Activities.Activity.DisplayName%2A>的标头中的值**CompensableActivity**活动设计器。 此外可以在中编辑**DisplayName**属性网格的框。

### <a name="the-compensableactivity-properties"></a>CompensableActivity 属性
 下表列出 <xref:System.Activities.Statements.CompensableActivity> 属性并说明如何在设计器中使用它们。 <xref:System.Activities.Activity.DisplayName%2A>和<xref:System.Activities.Activity%601.Result%2A>可在属性网格中编辑属性，但其他属性必须在工作流设计器图面上编辑。

|属性名|必需|用法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.CompensableActivity> 活动的可选友好名称。 默认值为 CompensableActivity。|
|<xref:System.Activities.Activity%601.Result%2A>|False|指定 <xref:System.Activities.Statements.CompensableActivity> 的返回值。 此属性必须在属性网格中进行编辑。|
|<xref:System.Activities.Statements.CompensableActivity.Body%2A>|True|指定为其提供补偿、取消和确认逻辑的活动。 若要添加<xref:System.Activities.Statements.CompensableActivity.Body%2A>活动，将活动从**工具箱**到**正文**框**CompensableActivity**活动设计器。 添加提示文本"此处放置活动"。|
|<xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A>|False|指定一个取消时执行的活动。 若要添加活动，删除其设计器从**工具箱**到**拖放**框**CompensableActivity**活动设计器。 添加提示文本"此处放置活动"。|
|<xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>|False|指定补偿 <xref:System.Activities.Statements.CompensableActivity.Body%2A> 活动时要执行的活动。 可使用 <xref:System.Activities.Statements.Compensate> 活动显式调用此处理程序。<br /><br /> 若要添加活动，删除其活动设计器从**工具箱**到**CompensationHandler**框**CompensableActivity**活动设计器。 添加提示文本"此处放置活动"。|
|<xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>|False|指定确认 <xref:System.Activities.Statements.CompensableActivity.Body%2A> 活动时要执行的活动。 可使用 <xref:System.Activities.Statements.Confirm> 活动显式调用此处理程序。<br /><br /> 若要添加活动，删除其活动设计器从**工具箱**到**ConfirmationHandler**框**CompensableActivity**活动设计器。 添加提示文本"此处放置活动"。|

## <a name="see-also"></a>请参阅

- [事务](../workflow-designer/transaction-activity-designers.md)
- [CancellationScope](../workflow-designer/cancellationscope-activity-designer.md)
- [补偿](../workflow-designer/compensate-activity-designer.md)
- [确认](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)