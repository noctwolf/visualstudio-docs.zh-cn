---
title: 工作流设计器-InvokeDelegate
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- InvokeDelegate Designer
- System.Activities.Statements.InvokeDelegate.UI
ms.assetid: 289a7498-5127-453f-beb5-05f05b80d26f
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 3d68fa1b777663ff8975f8ce99100d8eddc5f05d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31976914"
---
# <a name="invokedelegate"></a>InvokeDelegate

**InvokeDelegate**设计器用于创建和配置<xref:System.Activities.Statements.InvokeDelegate>活动。

## <a name="the-invokedelegate-activity"></a>InvokeDelegate 活动

<xref:System.Activities.Statements.InvokeDelegate> 调用公共委托。

### <a name="using-the-invokedelegate-activity-designer"></a>使用 InvokeDelegate 活动设计器

**InvokeDelegate**在找不到活动设计器**基元**类别**工具箱**，通过单击访问的哪一**工具箱**选项卡上的工作流设计器 (或者，选择**工具栏**从**视图**菜单上或 CRTL + ALT + X。)

**InvokeDelegate**活动设计器可以拖动从**工具箱**和放置到工作流设计器图面，在任何位置通常放置活动的如内<xref:System.Activities.Statements.Sequence>。 这将创建具有 InvokeDelegate 的默认 <xref:System.Activities.Statements.InvokeDelegate> 的 <xref:System.Activities.Activity.DisplayName%2A> 活动。 <xref:System.Activities.Activity.DisplayName%2A>可以在的标头中编辑**InvokeDelegate**活动设计器中或在**DisplayName**属性网格的框。

### <a name="the-invokedelegate-properties"></a>InvokeDelegate 属性

下表列出 <xref:System.Activities.Statements.InvokeDelegate> 属性并说明如何在设计器中使用它们。 可以在属性网格中编辑这些属性和一些可以在工作流 Designerdesigner 图面上编辑。

|属性名|必需|用法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|<xref:System.Activities.Statements.InvokeDelegate> 活动的友好名称。 默认值为 InvokeDelegate。<br /><br /> 虽然 <xref:System.Activities.Activity.DisplayName%2A> 不是绝对必需的，但最好使用该属性。|
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|True|要在执行活动时调用的 <xref:System.Activities.ActivityDelegate> 的名称。 此属性可以在设计器图面上进行编辑。 此属性是强制属性。|
|<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|调用委托的自变量集合。 密钥的参数对象的名称位于<xref:System.Activities.ActivityDelegate>和值是其表达式将进行计算并分配给相应的参数对象的参数。 在属性网格中，单击中的省略号按钮**DelegateArguments**字段，它显示**DelegateArguments**对话框以便您设置此属性。 单击**创建自变量**字段以添加参数。|

## <a name="see-also"></a>请参阅

- [如何：在工作流设计器中定义和使用活动委托](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)