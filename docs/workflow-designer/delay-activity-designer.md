---
title: 工作流设计器-Delay 活动设计器
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Delay.UI
ms.assetid: f51742a8-2c9a-47d1-8a23-18459d03ae19
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e22c80712bcb0c792fb929ae85b84912122a0bc
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31971642"
---
# <a name="delay-activity-designer"></a>Delay 活动设计器

**延迟**活动设计器用于创建和配置<xref:System.Activities.Statements.Delay>活动。

## <a name="the-delay-activity"></a>Delay 活动

<xref:System.Activities.Statements.Delay> 活动可将工作流的执行延迟指定时长。

### <a name="using-the-delay-activity-designer"></a>使用 Delay 活动设计器

**延迟**在找不到活动设计器**基元**类别**工具箱**，通过单击访问的哪一**工具箱**工作流设计器选项卡 (或者，选择**工具栏**从**视图**菜单上或 CTRL + ALT + X。)

**延迟**活动设计器可以拖动从**工具箱**和放置到工作流设计器图面，只要通常放置活动的如内<xref:System.Activities.Statements.Sequence>。 这将创建具有 Delay 的默认 <xref:System.Activities.Statements.Delay> 的 <xref:System.Activities.Activity.DisplayName%2A> 活动。 <xref:System.Activities.Activity.DisplayName%2A>可以在的标头中编辑**延迟**活动设计器中或在**DisplayName**属性网格的框。

### <a name="the-delay-properties"></a>Delay 属性

下表列出 <xref:System.Activities.Statements.Delay> 属性并说明如何在设计器中使用它们。 可以在属性网格中编辑这些属性，其中一些可以编辑工作流 Designerdesigner 图面上。

|属性名|必需|用法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.Delay> 活动的友好名称。 默认值为 Delay。 虽然 <xref:System.Activities.Activity.DisplayName%2A> 值不是绝对必需的，但最好使用该属性值。|
|<xref:System.Activities.Statements.Delay.Duration%2A>|True|将工作流延迟的时长。 此属性在属性网格中设置。 键入 00:00:00 格式的文本 <xref:System.TimeSpan> 或 Visual Basic 表达式来指定时长。|

## <a name="see-also"></a>请参阅

- [基元](../workflow-designer/primitives-activity-designers.md)
- [Assign](../workflow-designer/assign-activity-designer.md)
- [Delay 活动设计器](../workflow-designer/delay-activity-designer.md)
- [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)
- [WriteLine](../workflow-designer/writeline-activity-designer.md)