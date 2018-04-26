---
title: 工作流设计器-ParallelForEach&lt;T&gt;活动设计器
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.ParallelForEach`1.UI
ms.assetid: e93a4843-aef2-4d3e-9a0a-a2d3d1411aa7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bfd7d3220bc67b764b96033ad516eb857bec6014
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="parallelforeach-activity-designer"></a>ParallelForEach 活动设计器

<xref:System.Activities.Statements.ParallelForEach%601> 活动枚举集合元素并对集合中的每个元素并行执行嵌入语句，这将在同一线程上异步执行。 如果此活动的子活动预期会进入空闲状态，请使用此流控制活动，而不是 <xref:System.Activities.Statements.Sequence> 活动。

<xref:System.Activities.Statements.ParallelForEach%601>活动具有<xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>属性，它包含用户指定的 Visual Basic 表达式。 <xref:System.Activities.Statements.ParallelForEach%601> 活动在完成每个分支后计算此属性。 如果其计算结果为**true**，则<xref:System.Activities.Statements.ParallelForEach%601>活动完成，无需执行其他分支。 如果<xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>的计算结果不**true**，则<xref:System.Activities.Statements.ParallelForEach%601>活动完成其所有子活动后完成。

## <a name="the-parallelforeacht-activity"></a>ParallelForEach < T\>活动

<xref:System.Activities.Statements.ParallelForEach%601> 枚举其值并为枚举的每个值安排 <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> 的执行顺序。 仅安排 <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> 的执行顺序。 Body 的执行方式取决于 <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> 是否进入空闲状态。

如果 <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> 未进入空闲状态，则会按相反顺序执行，因为安排的活动作为堆栈来处理，最后安排的活动最先执行。 例如，如果你有一系列{1,2,3,4}中<xref:System.Activities.Statements.ParallelForEach%601>并用**WriteLine**作为写出值的 body。则会在控制台中依次打印出 4、3、2、1。 这是因为**WriteLine**不会在 4 后空闲， **WriteLine**安排活动、 它们执行使用堆栈行为 （先进后出）。

但是如果 <xref:System.Activities.Statements.ParallelForEach%601.Body%2A> 中有会进入空闲状态的活动，如 <xref:System.ServiceModel.Activities.Receive> 活动或 <xref:System.Activities.Statements.Delay> 活动， 那么就不需要等待它们完成。 <xref:System.Activities.Statements.ParallelForEach%601> 转至下一个预定的主体活动，并尝试执行它。 如果该活动也进入空闲状态，则 <xref:System.Activities.Statements.ParallelForEach%601> 将再移到下一个 Body 活动。

### <a name="using-the-parallelforeacht-activity-designer"></a>使用 ParallelForEach\<T > 活动设计器

**ParallelForEach\<T >** 在找不到活动设计器**控制流**类别**工具箱**，这通过单击访问**工具箱**工作流设计器左侧的选项卡 (或者，选择**工具栏**从**视图**菜单上或 CTRL + ALT + X。)

**ParallelForEach\<T >** 活动设计器可以拖动从**工具箱**和放置到工作流设计器图面，只要通常放置活动设计器，为示例、 内部的**序列**活动设计器。 将它放到工作流设计器中，完成后，它创建<xref:System.Activities.Statements.ParallelForEach%601>活动，其中默认情况下包含<xref:System.Activities.Activity.DisplayName%2A>的**ParallelForEach < Int32\>。**

### <a name="parallelforeacht-properties-in-the-workflow-designer"></a>ParallelForEach < T\>工作流设计器中的属性

下表列出最有用的 <xref:System.Activities.Statements.ParallelForEach%601> 活动属性并说明如何在设计器中使用它们。

|属性名|必需|用法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|指定活动设计器在标头中的友好显示名称。 默认值是**ParallelForEach\<Int32 >**。 值可以在中根据需要编辑**属性**网格或直接在活动设计器标头。|
|<xref:System.Activities.Statements.ParallelForEach%601.Body%2A>|False|要为集合中的每一项执行的活动。 若要添加<xref:System.Activities.Statements.ParallelForEach%601.Body%2A>活动，将活动从工具箱拖到**正文**框**ParallelForEach\<T >** 带提示文本"此处放置活动"的活动设计器。|
|**TypeArgument**|True|中的项的类型<xref:System.Activities.Statements.ParallelForEach%601.Values%2A>由泛型参数指定的集合*T*。默认情况下， **TypeArgument**设置为**Int32**。 若要更改中的类型 T **ParallelForEach < T\>** 活动设计器中，更改的值**TypeArgument**在属性网格中的组合框。|
|<xref:System.Activities.Statements.ParallelForEach%601.Values%2A>|True|要循环访问的项的集合。 若要设置<xref:System.Activities.Statements.ParallelForEach%601.Values%2A>，键入在 Visual Basic 表达式**值**框**ForEach < T\>** 带提示文本"输入 VB 表达式"文本框中或中的活动设计器**值**框**属性**窗口。|
|<xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>||在每个迭代完成后计算。 如果其计算结果为 true，则取消已安排的挂起的迭代。 如果未设置此属性，则所有安排的语句都将执行，直至完成为止。|

默认情况下，循环迭代器是命名项。 你可以更改中的迭代器变量的名称**ForEach**框中**ParallelForEach\<T >** 活动设计器。 循环迭代器可在 <xref:System.Activities.Statements.ParallelForEach%601> 活动的子级中的表达式中使用。

## <a name="see-also"></a>请参阅

- [序列](../workflow-designer/sequence-activity-designer.md)
- [并行](../workflow-designer/parallel-activity-designer.md)
- [控制流](../workflow-designer/control-flow-activity-designers.md)