---
title: 工作流设计器-如何： 创建工作流控制台应用程序
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 51a2eea7-921c-49f1-b358-68afc27f1ee9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6461a644bdedd3d391059cd8a3a17f887e77c6b3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-workflow-console-application"></a>如何：创建工作流控制台应用程序

Windows Workflow Foundation (WF)，可为执行系统或人工流程创建工作流。 Windows 工作流设计器提供用于创建这些工作流设计图面。 工作流设计器可以用于创建从 Visual Studio 中的工作流，或它可以集成到重新承载设计器的其他应用程序。

本主题介绍如何在 Visual Studio 2010 中使用工作流设计器创建的工作流控制台应用程序中。

## <a name="to-create-a-workflow-console-application"></a>创建工作流控制台应用程序

1.  启动 Visual Studio 2010。

2.  在“文件”菜单上，指向“新建”，然后选择“项目”。

     **“新建项目”** 对话框随即打开。

3.  在**已安装的模板**窗格中，选择**工作流**从**Visual C#** 或**Visual Basic**分组，具体取决于你语言首选项。

4.  在中间窗格中，选择**工作流控制台应用程序**。

5.  在**名称**框中，输入你的项目，以便可以方便地标识的描述性名称。

6.  在**位置**框中，输入你要在其中保存你的项目，或单击的目录**浏览**以导航到。

7.  在**解决方案**框中，输入新的解决方案的名称。 单击**确定**创建应用程序。

    > [!NOTE]
    > 如果你想要添加到现有的解决方案的工作流控制台应用程序，在 Visual Studio 2010 中打开该解决方案，右键单击该解决方案中的**解决方案资源管理器**，然后选择**添加**，然后**新项目**以打开**新项目**对话框。 按照此过程中的上述步骤继续操作。

8.  该项目模板将在 XAML 中创建一个工作流定义并在源代码中创建控制台应用程序定义。 工作流设计器打开并显示你创建的工作流的画布。

9. 若要编写工作流，将活动或其他工作流项从**工具箱**到你的工作流中的设计图面。

## <a name="see-also"></a>请参阅

- [创建工作流项目](../workflow-designer/creating-a-workflow-project.md)