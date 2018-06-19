---
title: 工作流设计器-选择条件对话框 （旧版）
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
f1_keywords:
- System.Workflow.Activities.Rules.Design.ConditionBrowserDialog.UI
helpviewer_keywords:
- Select Condition dialog box
ms.assetid: fe3b415c-cb55-4295-b853-3f40765b28d0
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 836cd63ecaa19be46617422d3cede2f04291992e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31976470"
---
# <a name="select-condition-dialog-box-legacy"></a>“选择条件”对话框（旧版）

本主题介绍如何使用**选择条件**旧的 Windows 工作流设计器中的对话框。 当你需要以面向.NET Framework 版本 3.5 或 WinFX 时，请使用旧工作流设计器。

**选择条件**对话框用于选择要分配给活动的 condition 属性的声明性规则条件。 这些规则条件作为以下 Windows Workflow Foundation 现成可用的活动属性被公开：

-   [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)

-   [IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)

-   [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)

-   [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)

有关如何访问**选择条件**对话框中，请参阅[如何： 创建声明性规则条件 （旧版）](../workflow-designer/how-to-create-a-declarative-rule-condition-legacy.md)。

下表描述的用户界面 (UI) 元素**选择条件**对话框。

|UI 元素|描述|
|----------------|-----------------|
|**新增功能。。。**|单击此项可打开[规则条件编辑器对话框 （旧版）](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)创建新的规则条件。|
|**编辑...**|单击此项可打开[规则条件编辑器对话框 （旧版）](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)编辑选定的规则条件。|
|重命名...|单击可打开用于重命名选定的规则条件的对话框。|
|**删除**|单击可删除选定的规则条件。|
|**条件预览**|显示选定的规则条件的条件表达式。|
|**还行**|单击可将选定的规则条件分配给活动的条件。|

 有关创建和编辑规则条件的详细信息，请参阅[规则条件编辑器对话框 （旧版）](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)。

 有关条件的详细信息，请参阅[在工作流中使用条件](http://go.microsoft.com/fwlink?LinkID=65009)。

## <a name="see-also"></a>请参阅

- [“规则条件编辑器”对话框（旧版）](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)
- [如何：创建声明性规则条件（旧版）](../workflow-designer/how-to-create-a-declarative-rule-condition-legacy.md)
- [工作流中使用条件](http://go.microsoft.com/fwlink?LinkID=65009)
- [使用 ConditionedActivityGroup 活动](http://go.microsoft.com/fwlink?LinkID=65066)
- [使用 IfElseBranchActivity 活动](http://go.microsoft.com/fwlink?LinkID=65075)
- [使用 ReplicatorActivity 活动](http://go.microsoft.com/fwlink?LinkID=65080)
- [使用 WhileActivity 活动](http://go.microsoft.com/fwlink?LinkID=65091)
- [Windows Workflow Foundation 的旧版设计器 UI 帮助](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)