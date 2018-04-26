---
title: 工作流设计器-CancellationScope 活动设计器
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.CancellationScope.UI
ms.assetid: 2c85d663-b219-4142-9866-7693ffd46379
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a0f9a40434821294384154ddcbbfebbd0a7885eb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="cancellationscope-activity-designer"></a>CancellationScope 活动设计器

**CancellationScope**活动设计器用于创建和配置<xref:System.Activities.Statements.CancellationScope>活动。

## <a name="the-cancellationscope-activity"></a>CancellationScope 活动
 使用 <xref:System.Activities.Statements.CancellationScope> 活动可指定要执行的活动以及该活动的取消逻辑。

### <a name="using-the-cancellationscope-activity-designer"></a>使用 CancellationScope 活动设计器
 **CancellationScope**在找不到活动设计器**事务**类别**工具箱**。 若要打开**工具箱**，选择**工具箱**工作流设计器选项卡。 或者，选择**工具栏**从**视图**菜单上或按 CTRL + ALT + X。

 **CancellationScope**活动设计器可以拖动从**工具箱**和放置到工作流设计器图面，只要放置活动的如内<xref:System.Activities.Statements.Sequence>。 删除**CancellationScope**活动设计器创建<xref:System.Activities.Statements.CancellationScope>默认值的活动<xref:System.Activities.Activity.DisplayName%2A>CancellationScope。 编辑<xref:System.Activities.Activity.DisplayName%2A>的标头中的值**CancellationScope**活动设计器。 你还可以编辑在**DisplayName**属性网格的框。

### <a name="the-cancellationscope-properties"></a>CancellationScope 属性
 下表列出 <xref:System.Activities.Statements.CancellationScope> 属性并说明如何在设计器中使用它们。 <xref:System.Activities.Activity.DisplayName%2A>可在属性网格中编辑属性，但其他属性必须在工作流设计器图面上编辑。

|属性名|必需|用法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.CancellationScope> 活动的可选友好名称。 默认值为 CancellationScope。 虽然 <xref:System.Activities.Activity.DisplayName%2A> 值不是绝对必需的，但最好使用该属性值。|
|<xref:System.Activities.Statements.CancellationScope.Body%2A>|True|指定为其提供取消逻辑的活动。 若要添加<xref:System.Activities.Statements.CancellationScope.Body%2A>活动，将活动从**工具箱**到**正文**框**CancellationScope**活动设计器。 添加提示文本"此处放置活动"。|
|<xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>|True|指定如果没有取消，则执行的活动。 若要添加<xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>活动，将活动从**工具箱**到**拖放**框**CancellationScope**活动设计器。 添加提示文本"此处放置活动"。|

## <a name="see-also"></a>请参阅

- [事务](../workflow-designer/transaction-activity-designers.md)
- [CompensableActivity](../workflow-designer/compensableactivity-activity-designer.md)
- [补偿](../workflow-designer/compensate-activity-designer.md)
- [确认](../workflow-designer/confirm-activity-designer.md)
- [TransactionScope](../workflow-designer/transactionscope-activity-designer.md)