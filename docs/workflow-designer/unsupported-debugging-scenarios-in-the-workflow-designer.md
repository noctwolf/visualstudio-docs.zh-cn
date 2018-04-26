---
title: 工作流设计器中不受支持的调试方案
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 6adbe379-41d0-4681-9cd0-b91f187c3c2c
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 2b876df1b7d997f3999c119d02abd593a88e6d5e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>工作流设计器中不受支持的调试方案

在.NET Framework 4 工作流设计器添加许多新功能，但仍存在一些它不支持的调试方案。

以下是不受支持工作流设计器调试方案：

-   在编辑代码之后不能继续执行。

-   不能从工作流中的任意点继续执行（“设置下一语句”）。

-   只有在到达光标处之后才能继续执行（“运行到光标处”）。

-   不能使用工作流设计器来调试通过代码创建（未使用工作流设计器）的工作流。

-   在早期版本的 Windows Workflow Foundation (WF) 中创建的工作流无法在.NET Framework 4 设计器中进行调试。

-   不能在两个活动或 <xref:System.Activities.Statements.Flowchart> 节点之间的链接上定义断点。

-   调试期间剪贴板不可用。

-   复制或粘贴活动时不会保留断点。

-   不能在调用堆栈窗口中设置工作流断点。

-   在设计器中创建断点时**行**和**字符**中的设置**新断点**不使用对话框。

-   “断点”窗口或快捷菜单不支持以下用于工作流调试的列或选项：

    -   条件

    -   命中次数

    -   命中条件

    -   函数

    -   数据

    -   进程

    -   转到反汇编