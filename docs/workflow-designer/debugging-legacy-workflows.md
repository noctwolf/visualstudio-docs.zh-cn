---
title: 调试旧版工作流 |Microsoft 文档
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflows, debugging
- debugging, workflows
- debugging workflows
ms.assetid: e6097b47-760a-4b30-a92c-ae70cdbda49f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2710266446e285d9107f4450c09ffe2e8e87e090
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="debugging-legacy-workflows"></a>调试旧版工作流

如果你使用中的旧 Windows 工作流设计器[!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)]生成[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]，面向.net Framework 3.0 或 3.5，你可以通过设置断点、 附加到进程、 检查调试工作流与任何其他程序类似的应用程序线程和调用堆栈。 您还可以选择远程调试。

> [!NOTE]
> 如果计算机上安装并卸载过 Visual Studio 的多个版本，在以下两种情况下 WF3 调试可能失败：
>
> -   设置的断点未命中。
> -   显示以下消息：
>
> **无法启动 web 服务器上进行调试。调试程序安装不正确。无法对请求的代码类型进行调试。运行安装程序以安装或修复调试器。**
>
> 如果在调试 .NET Framework 3.0 或 3.5 工作流时发生以上任一情况，请对 Visual Studio 安装进行修复。

 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] 集成具有以下标准 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 调试窗口：

-   **断点**： 按预期工作，但你指定的函数名称的活动。

-   **调用堆栈**： 已修改，以提供工作流实例中执行的活动的概述。 中的条目**调用堆栈**窗口是深度优先搜索得出的执行的活动。 您可以双击某个项以将焦点放在选定的活动上。

-   **线程**： 提供正在调试的工作流实例的实例 ID。

 Visual Studio for Windows Workflow Foundation 不支持以下调试功能：

-   设计器图面上的条件断点。

-   QuickWatch。

-   设置下一语句。

-   运行到光标处。

-   编辑并继续。

-   实时调试。

-   混合模式调试。