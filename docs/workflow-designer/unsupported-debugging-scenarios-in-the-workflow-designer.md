---
title: 工作流设计器中不受支持的调试方案
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 6adbe379-41d0-4681-9cd0-b91f187c3c2c
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 83c9b1158319b580bc860982b6c51c9c28edf5af
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60099645"
---
# <a name="unsupported-debugging-scenarios-in-the-workflow-designer"></a>工作流设计器中不受支持的调试方案

在.NET Framework 4 工作流设计器添加许多新功能，但仍有不支持某些调试方案。

以下是不受支持工作流设计器调试方案：

- 在编辑代码之后不能继续执行。

- 不能从工作流中的任意点继续执行（“设置下一语句”）。

- 只有在到达光标处之后才能继续执行（“运行到光标处”）。

- 不能使用工作流设计器来调试通过代码创建（未使用工作流设计器）的工作流。

- 在早期版本的 Windows Workflow Foundation (WF) 中创建的工作流不能在.NET Framework 4 设计器中进行调试。

- 不能在两个活动或 <xref:System.Activities.Statements.Flowchart> 节点之间的链接上定义断点。

- 调试期间剪贴板不可用。

- 复制或粘贴活动时不会保留断点。

- 不能在调用堆栈窗口中设置工作流断点。

- 在设计器中创建断点时**行**并**字符**中的设置**新断点**不使用对话框。

- “断点”窗口或快捷菜单不支持以下用于工作流调试的列或选项：

    - 条件

    - 命中次数

    - 命中条件

    - 函数

    - 数据

    - 进程

    - 转到反汇编