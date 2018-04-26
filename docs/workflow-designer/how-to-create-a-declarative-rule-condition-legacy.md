---
title: 工作流设计器-如何： 创建声明性规则条件 （旧版）
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- declarative rule conditions
- condition statements, declarative rule conditions
- Rule Condition Editor dialog box
ms.assetid: 804b6129-c433-408f-a424-46987967730c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 43b359040256788db240274f43f706b41f01d021
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-declarative-rule-condition-legacy"></a>如何：创建声明性规则条件（旧版）

本主题介绍如何对.NET Framework 3.5 或 WinFX 声明使用该目标的旧的 Windows 工作流设计器的规则条件。

条件语句的计算结果为**True**或**False**。 声明性规则条件是通过创建一个条件语句[规则条件编辑器对话框 （旧版）](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)并将存储为 XML 与工作流。 声明性规则条件可以包括一些谓词，这些谓词比较工作流状态和组合多个谓词的布尔代数。

声明性规则条件用在以下 Windows Workflow Foundation 现成可用的活动中：

-   [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)

-   [IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)

-   [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)

-   [WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)

-   [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040)

-   [StateMachineWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65045)

## <a name="to-create-a-declarative-rule-condition-using-the-rule-condition-editor"></a>使用规则条件编辑器创建声明性规则条件

1.  在活动的**属性**窗口中，单击**条件**属性或**UntilCondition**属性，具体取决于该活动。

2.  选择**声明性规则条件**从属性列表。

3.  展开**条件**或**UntilCondition**属性。

4.  单击**ConditionName**属性。

5.  单击**ConditionName**省略号 **[…]** 以打开**选择条件**对话框。

6.  单击**新条件**以打开**规则条件编辑器**对话框。

7.  键入的表达式中的条件**条件**文本框。

     有关如何创建条件表达式的信息，请参阅[规则条件编辑器对话框 （旧版）](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)。

8.  在你完成创建条件表达式，请单击**确定**关闭对话框并使用分配的名称创建的规则条件。

     **选择条件**对话框随即打开。

     有关如何使用信息**选择条件**对话框中，请参阅[选择条件对话框 （旧版）](../workflow-designer/select-condition-dialog-box-legacy.md)。

## <a name="see-also"></a>请参阅

- [旧版工作流活动](../workflow-designer/legacy-workflow-activities.md)
- [使用 ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65066)
- [使用 IfElseBranchActivity 活动](http://go.microsoft.com/fwlink?LinkID=65075)
- [使用复制器活动](http://go.microsoft.com/fwlink?LinkID=65080)
- [使用 While 活动](http://go.microsoft.com/fwlink?LinkID=65091)
- [“规则条件编辑器”对话框（旧版）](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)
- [“选择条件”对话框（旧版）](../workflow-designer/select-condition-dialog-box-legacy.md)
- [工作流中使用条件](http://go.microsoft.com/fwlink?LinkID=65009)