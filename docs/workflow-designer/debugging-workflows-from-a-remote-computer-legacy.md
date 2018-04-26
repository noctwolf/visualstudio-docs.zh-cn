---
title: 工作流设计器-调试工作流从远程计算机 （旧版）
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, debugging remotely
- debugging workflows, remotely
- remote debugging, workflows
- debugging, remote
ms.assetid: 44eaec8f-9959-4ae7-a374-670946f933c1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 391180cd76fe5e0cccca802ba1cbfb78277dabc1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="debugging-workflows-from-a-remote-computer-legacy"></a>通过远程计算机调试工作流（旧版）

本主题介绍如何调试远程旧的 Windows Workflow Foundation (WF) 应用程序都用旧的 Windows 工作流设计器生成。 当你的应用程序需要以面向.NET Framework 版本 3.5 或 WinFX 时，请使用旧工作流设计器。

 在安装 Visual Studio 时，组件安装选项之一是安装 Visual Studio 调试器的 Windows Workflow Foundation (WF)。 这将安装远程调试组件。 必须在将要进行远程工作流调试的目标计算机上安装这些远程调试组件。

 另外，必须在用于调试的本地计算机的全局程序集缓存 (GAC) 中安装程序集，该程序集包含将在远程计算机上进行调试的旧工作流的工作流定义。 例如，如果旧工作流在远程计算机 A 上运行，而您正在从本地计算机 B 对其进行调试，则计算机 B 的 GAC 中必须存在工作流定义。这样，设计器可以将正在计算机 A 上远程运行的工作流的工作标记反序列化并将其显示在计算机 B 上。有关全局程序集缓存的更多信息，请参见 MSDN Library。

 Windows Workflow Foundation 远程调试与其他 Visual Studio 组件远程调试的功能相同。 有关详细信息，请参阅 Visual Studio 远程调试 MSDN 库中。

## <a name="see-also"></a>请参阅

- [调试旧版工作流](../workflow-designer/debugging-legacy-workflows.md)