---
title: 工作流设计器-如何： 向工作流项目添加新项
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 5c6180ca-af10-4513-b0cb-7d478fd84eab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0aa2be7fd8ecccbd8de0aa54c2693dd6b02c7e10
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31971632"
---
# <a name="how-to-add-a-new-item-to-a-workflow-project"></a>如何：向工作流项目添加新项

创建工作流项目后，可以将工作流活动、 设计器和其他熟悉的 Visual Studio 项添加到你的项目。

下表列出了你可以添加到工作流项目的 Windows Workflow Foundation (WF) 项目。

|名称|描述|
|----------|-----------------|
|Activity|由其他活动组成的活动。 选择此项将相同的 XAML 文件添加到项目，选择时要获得**活动库**新项目的模板。 有关此过程的详细信息，请参阅[如何： 创建活动库](../workflow-designer/how-to-create-an-activity-library.md)。|
|活动设计器|用于自定义活动的设计时体验的设计器。 选择此项将相同的文件添加到项目，选择时要获得**活动设计器库**新项目的模板。 有关此过程的详细信息，请参阅[如何： 创建活动设计器库](../workflow-designer/how-to-create-an-activity-designer-library.md)。|
|Code 活动|一个采用代码编写执行逻辑的活动。 已为您生成一个源代码文件，该文件带有 <xref:System.Activities.CodeActivity.Execute%2A> 方法的重写。|
|WCF 工作流服务|使用工作流活动生成的 [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] 服务。 选择此项将相同的文件添加到项目，选择时要获得**WCF 工作流服务应用程序**新项目的模板。 有关此过程的详细信息，请参阅[如何： 创建 WCF 工作流服务应用程序](../workflow-designer/how-to-create-a-wcf-workflow-service-application.md)。|

## <a name="to-add-a-new-item-to-a-workflow-project"></a>向工作流项目添加新项

1.  上**项目**菜单上，单击**添加新项...**.

     **添加新项**对话框随即打开。

2.  在**已安装的模板**窗格中，选择**工作流**组。

3.  选择四项中的一项。 上表列出了可用的选项。

4.  键入正确的名称中的项**名称**底部的对话框中的框。

5.  单击**添加**将项添加到当前的工作流项目。

## <a name="see-also"></a>请参阅

- [创建工作流项目](../workflow-designer/creating-a-workflow-project.md)