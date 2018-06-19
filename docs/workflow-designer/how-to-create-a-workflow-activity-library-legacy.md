---
title: 工作流设计器-如何： 创建工作流活动库 （旧版）
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, activity library projects
- workflow activity libraries
- projects, workflow activity libraries
ms.assetid: fb5aa940-2ae8-4b52-b52c-51c20861a7b4
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 432766e60ee1384db0f8cd5bad1f369e80ddd20a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31973162"
---
# <a name="how-to-create-a-workflow-activity-library-legacy"></a>如何：创建工作流活动库（旧版）

请按照下列步骤创建使用 Windows 工作流设计器提供的 Visual Studio 2010 的旧工作流活动库项目。 当你需要以面向.NET Framework 版本 3.5 或 WinFX 时，请使用旧工作流设计器。

## <a name="to-create-a-workflow-activity-library-project"></a>创建一个工作流 Activity 库项目

1.  启动 Visual Studio。

2.  在“文件”菜单上，指向“新建”，然后选择“项目”。

     **“新建项目”** 对话框随即打开。

3.  选择 **.NET Framework 3.0**选项或 **.NET Framework 3.5**的下拉列表的顶部列表中的选项**新项目**窗口，以访问旧设计器。

    > [!NOTE]
    > Visual Studio 2010 中的默认选项才 **.NET Framework 4**。 此选项可用于创建面向.NET Framework 4 的 Windows Workflow Foundation (WF) 应用程序并不使用旧设计器。

4.  在**项目类型**窗格中，选择 Visual C# 或 Visual Basic (下**其他语言**)，然后选择**工作流**。

5.  在**模板**窗格中，选择**工作流活动库**。

6.  在**名称**框中，输入你的项目，以便可以方便地标识的描述性名称。

7.  在**位置**框中，输入你要在其中保存你的项目，或单击的目录**浏览**以导航到。

     如果要为项目创建解决方案目录，请选择**创建解决方案的目录**复选框，输入中的名称**解决方案名称**框。

8.  单击 **“确定”**。

## <a name="see-also"></a>请参阅

- [创建旧版工作流项目](../workflow-designer/creating-legacy-workflow-projects.md)
- [使用旧版活动设计器](../workflow-designer/using-the-legacy-activity-designer.md)
- [旧版工作流活动](../workflow-designer/legacy-workflow-activities.md)
- [开发工作流活动](http://msdn.microsoft.com/en-us/19876dfc-dfa5-4d52-b1f5-1d087474cc52)
- [Windows Workflow Foundation 活动](http://msdn.microsoft.com/en-us/192c4c1e-afb6-4f58-ab11-2b5bbbc2d2c0)