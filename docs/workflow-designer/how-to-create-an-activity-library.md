---
title: 工作流设计器-如何： 创建活动库
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 1eeebe74-7303-4345-8a83-fe37a26bc84b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ef62a5098581042a4995d6c522e0757c361e9d4f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31974039"
---
# <a name="how-to-create-an-activity-library"></a>如何：创建活动库
自定义活动用于在工作流中对特定业务流程进行建模。 提供了 Visual Studio 2010 中的活动库模板，用于使你能够创建此类自定义活动，以可视方式使用 Windows 工作流设计器。

### <a name="to-create-a-workflow-activity-library"></a>创建工作流活动库

1.  启动 Visual Studio 2010。

2.  在“文件”菜单上，指向“新建”，然后选择“项目”。

     **“新建项目”** 对话框随即打开。

3.  在**项目类型**窗格中，选择**工作流**从**Visual C#** 项目或**Visual Basic**分组，具体取决于你语言首选项。

4.  在**模板**窗格中，选择**活动库**。

5.  在**名称**框中，键入你的项目的描述性名称以便可以方便地标识。

6.  在**位置**框中，键入想要保存你的项目，或单击的目录中**浏览**以导航到。

7.  在**解决方案**框中，键入你的解决方案的描述性名称，然后单击**确定**。

    > [!NOTE]
    > 如果你想要添加到现有的解决方案的工作流控制台应用程序，在 Visual Studio 2010 中打开该解决方案，右键单击该解决方案中的**解决方案资源管理器**，然后选择**添加**，然后**新项目**以打开**新项目**对话框。 按照此过程中的上述步骤继续操作。

8.  该项目模板将创建一个 XAML 格式的活动定义。 Windows 工作流设计器打开并显示自定义活动的画布。

9. 将活动从**工具箱**到设计图面可将其包括在你自定义活动。

    > [!CAUTION]
    > 自定义活动的主体中只能有一个子活动；但是，该子活动可以是一个复合活动，如 <xref:System.Activities.Statements.Sequence> 活动或 <xref:System.Activities.Statements.Flowchart> 活动。

## <a name="see-also"></a>请参阅

- [如何：创建活动](/dotnet/framework/windows-workflow-foundation/how-to-create-an-activity)
- [创建工作流项目](../workflow-designer/creating-a-workflow-project.md)