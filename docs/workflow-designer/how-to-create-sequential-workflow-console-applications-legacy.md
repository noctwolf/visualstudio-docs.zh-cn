---
title: 工作流设计器-如何： 创建顺序工作流控制台应用程序 （旧版）
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, console applications
- sequential workflows, console applications
- console applications, sequential workflow
ms.assetid: 9f7be7fa-551f-42c6-a9bb-f5ae8ab83625
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fb4e048fdf8eb8fee541f84656a29427b5a07a1d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31973214"
---
# <a name="how-to-create-sequential-workflow-console-applications-legacy"></a>如何：创建顺序工作流控制台应用程序（旧版）

按照这些步骤创建使用 Windows 工作流设计器提供的 Visual Studio 2010 的旧的顺序工作流控制台应用程序项目。 当你需要以面向.NET Framework 版本 3.5 或 WinFX 时，请使用旧工作流设计器。

## <a name="to-create-a-sequential-workflow-console-application"></a>创建顺序工作流控制台应用程序

1.  启动 Visual Studio。

2.  在“文件”菜单上，指向“新建”，然后选择“项目”。

     **“新建项目”** 对话框随即打开。

3.  选择 **.NET Framework 3.0**选项或 **.NET Framework 3.5**的下拉列表的顶部列表中的选项**新项目**窗口，以访问旧设计器。

    > [!NOTE]
    > Visual Studio 2010 中的默认选项才 **.NET Framework 4**。 此选项可用于创建面向.NET Framework 4 的 Windows Workflow Foundation (WF) 应用程序并不使用旧设计器。

4.  在**项目类型**窗格中，选择 Visual C# 项目或 Visual Basic 项目 (下**其他语言**)，然后选择**工作流**。

5.  在**模板**窗格中，选择**顺序工作流控制台应用程序**。

6.  在**名称**框中，输入你的项目，以便可以方便地标识的描述性名称。

7.  在**位置**框中，输入你要在其中保存你的项目，或单击的目录**浏览**以导航到。

     Windows 窗体设计器将会打开并显示所创建项目的 Form1。

8.  单击 **“确定”**。

     工作流设计器将会打开并显示所创建的顺序工作流的工作流设计图面。

9. 将活动从**工具箱**到中的设计图面**放置活动**指定区域。

## <a name="see-also"></a>请参阅

- [创建旧版工作流项目](../workflow-designer/creating-legacy-workflow-projects.md)
- [开发工作流](http://msdn.microsoft.com/en-us/557bcb1f-a7ab-49f6-8df7-2706b7001301)