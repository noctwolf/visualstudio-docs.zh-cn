---
title: 工作流设计器-如何： 创建 WCF 工作流服务应用程序
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 12d675ac-27d8-4d86-ba16-6f7688f8c841
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93fb69862c228a3b6e61467facba188dd20c67c7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-wcf-workflow-service-application"></a>如何：创建 WCF 工作流服务应用程序

Windows Communication Foundation (WCF) 工作流服务应用程序是跨进程边界客户端和本身之间传递消息的分布式的通信服务。 服务端上的服务协定的实现以声明方式通过在.NET Framework 4 中的方式类似于在.NET Framework 3.5 的旧工作流服务的工作流活动。

## <a name="to-create-a-wcf-workflow-service-application"></a>创建 WCF 工作流服务应用程序

1.  启动 Visual Studio 2010。

2.  在“文件”菜单上，指向“新建”，然后选择“项目”。

     **“新建项目”** 对话框随即打开。

3.  在**已安装的模板**窗格中，选择**WCF**或**工作流**从**Visual C#** 或**Visual Basic**具体取决于选择的语言的分组。

4.  在中间窗格中，选择**WCF 工作流服务应用程序**。

5.  在**名称**框中，输入你的项目，以便可以方便地标识的描述性名称。

6.  在**位置**框中，输入你要在其中保存你的项目，或单击的目录**浏览**以导航到。

7.  在**解决方案**框中，选择创建新的解决方案，然后单击**确定**。

    > [!NOTE]
    > 如果你想要添加到现有的解决方案的工作流控制台应用程序，在 Visual Studio 2010 中打开该解决方案，右键单击该解决方案中的**解决方案资源管理器**，然后选择**添加**，然后**新项目**以打开**新项目**对话框。 按照此过程中的上述步骤继续操作。

8.  该项目模板将创建一个 XAML 格式的服务定义。 Windows 工作流设计器将打开到设计视图，其中<xref:System.Activities.Statements.Sequence>包含一组活动<xref:System.ServiceModel.Activities.Receive>和<xref:System.ServiceModel.Activities.SendReply>活动。

## <a name="see-also"></a>请参阅

- [如何：创建活动](/dotnet/framework/windows-workflow-foundation/how-to-create-an-activity)
- [创建工作流项目](../workflow-designer/creating-a-workflow-project.md)