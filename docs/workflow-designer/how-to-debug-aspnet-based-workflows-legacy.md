---
title: 工作流设计器-如何： 调试基于 ASP.NET 的工作流 （旧版）
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- ASP.NET, debugging workflows
- debugging workflows, ASP.NET workflows
- ASP.NET workflows, debugging
- debugging, ASP.NET workflows
ms.assetid: 79b21edc-9e7d-410d-af68-09c1598b9c30
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 7bf16a6a88c5d4cd063f1c32ca846031d8b2588d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31975867"
---
# <a name="how-to-debug-aspnet-based-workflows-legacy"></a>如何：调试基于 ASP.NET 的工作流（旧版）

本主题介绍如何调试基于 ASP.NET 的 Windows Workflow Foundation (WF) 应用程序，面向.NET Framework 版本 3.5 或 WinFX 旧的 Windows 工作流设计器中。

通过附加到承载工作流的进程，可以调试在 ASP.NET 中启动的旧工作流或以 Web 服务形式发布的旧工作流。

## <a name="to-debug-an-aspnet-based-workflow"></a>调试基于 ASP.NET 的工作流

1.  启用 ASP.NET 应用程序通过设置调试**调试 = true** web.config 文件中。

2.  将工作流库设置为启动项目，并在工作流上设置断点。

3.  在工作流项目属性中输入默认网页的 URL**调试**选项**与外部 URL 启动浏览器**文本框。

4.  选择**附加到进程**上**调试**菜单。

5.  选择要从附加到进程**可用进程**列表。

     附加到承载工作流的 w3wp.exe、webdev.webserver 或 aspnet_wp 进程。

6.  单击**选择**旁边**附加到**文本框。

     **选择代码类型**对话框随即出现。

7.  选择**调试以下代码类型**和选择**工作流**。

8.  单击 **“确定”**。

9. 单击 **“附加”**。

10. 打开浏览器中的默认网页并启动工作流。

## <a name="see-also"></a>请参阅

- [调用 Visual Studio Debugger for Windows Workflow Foundation（旧版）](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)
- [如何：在工作流中设置断点（旧版）](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md)
- [调试旧版工作流](../workflow-designer/debugging-legacy-workflows.md)