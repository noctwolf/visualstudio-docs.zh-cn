---
title: 工作流设计器-Throw 活动设计器
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Activities.Statements.Throw.UI
ms.assetid: 5e97c947-be39-4a1f-af04-000e2e09528a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 02bb94ad17b78b1264129b8a5ba00a964edbd2f2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="throw-activity-designer"></a>Throw 活动设计器

**引发**活动设计器用于创建和配置<xref:System.Activities.Statements.Throw>活动。

## <a name="the-throw-activity"></a>Throw 活动
 <xref:System.Activities.Statements.Throw> 活动会引发一个异常。

### <a name="using-the-throw-activity-designer"></a>使用 Throw 活动设计器
 **引发**在找不到活动设计器**错误处理**类别**工具箱**，通过单击访问的哪一**工具箱**工作流设计器左侧的选项卡 (或者，选择**工具栏**从**视图**菜单上或 CTRL + ALT + X。)

 **引发**活动设计器可以拖动从**工具箱**和放置到工作流设计器图面，只要通常放置活动的如内<xref:System.Activities.Statements.Sequence>。 这将创建<xref:System.Activities.Statements.Throw>默认值的活动**DisplayName**引发。 <xref:System.Activities.Activity.DisplayName%2A>可以在的标头中编辑值**引发**活动设计器中或在**DisplayName**属性网格的框。 <xref:System.Activities.Statements.Throw.Exception%2A> 属性必须在属性网格上编辑。

### <a name="the-throw-properties"></a>Throw 属性
 下表列出 <xref:System.Activities.Statements.Throw> 属性并说明如何在设计器中使用它们。

|属性名|必需|用法|
|-------------------|--------------|-----------|
|<xref:System.Activities.Activity.DisplayName%2A>|False|指定 <xref:System.Activities.Statements.Throw> 活动的可选友好名称。 默认值为 Throw。|
|<xref:System.Activities.Statements.Throw.Exception%2A>|True|要引发的异常。 此异常必须派生自 <xref:System.Exception>。 若要指定此异常，请在属性网格中键入 Visual Basic 表达式。|

## <a name="see-also"></a>请参阅

- [集合](../workflow-designer/collection-activity-designers.md)
- [重新引发](../workflow-designer/rethrow-activity-designer.md)
- [Throw 活动设计器](../workflow-designer/throw-activity-designer.md)
- [TryCatch](../workflow-designer/trycatch-activity-designer.md)