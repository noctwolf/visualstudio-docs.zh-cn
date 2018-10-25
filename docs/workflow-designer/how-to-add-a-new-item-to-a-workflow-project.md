---
title: 工作流设计器-如何： 向工作流项目添加新项
ms.date: 06/25/2018
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: 5c6180ca-af10-4513-b0cb-7d478fd84eab
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dbed404f2cdd69446d8945fc9ff96703eccd161f
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49814218"
---
# <a name="how-to-add-a-new-item-to-a-workflow-project"></a>如何： 向工作流项目添加新项

创建工作流项目后，可以将工作流活动、 设计器和其他熟悉的 Visual Studio 项添加到你的项目。

下表列出了可以添加到工作流项目的 Windows Workflow Foundation (WF) 项：


| name | 描述 |
|-| - |
| Activity | 由其他活动组成的活动。 选择此项将同一个 XAML 文件添加到项目，选择时要获得**活动库**新项目模板。 有关此过程的详细信息，请参阅[如何： 创建活动库](../workflow-designer/how-to-create-an-activity-library.md)。 |
| 活动设计器 | 用于自定义活动的设计时体验的设计器。 选择此项将相同文件添加到项目，选择时要获得**活动设计器库**新项目模板。 有关此过程的详细信息，请参阅[如何： 创建活动设计器库](../workflow-designer/how-to-create-an-activity-designer-library.md)。 |
| Code 活动 | 一个采用代码编写执行逻辑的活动。 已为您生成一个源代码文件，该文件带有 <xref:System.Activities.CodeActivity.Execute%2A> 方法的重写。 |
| WCF 工作流服务 | 使用工作流活动生成的 [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] 服务。 选择此项将相同文件添加到项目，选择时要获得**WCF 工作流服务应用程序**新项目模板。 有关此过程的详细信息，请参阅[如何： 创建 WCF 工作流服务应用程序](../workflow-designer/how-to-create-a-wcf-workflow-service-application.md)。 |

## <a name="to-add-a-new-item-to-a-workflow-project"></a>向工作流项目添加新项

1. 上**项目**菜单中，选择**添加新项**。

   此时将打开“添加新项”对话框。

1. 在左侧窗格中，选择**工作流**类别，并选择工作流项目模板。

   > [!NOTE]
   > 如果没有看到**工作流**类别中，首次安装**Windows Workflow Foundation**组件的 Visual Studio 2017。 有关详细说明，请参阅[安装 Windows Workflow Foundation](developing-applications-with-the-workflow-designer.md#install-windows-workflow-foundation)。

1. 输入中的项的名称**名称**对话框底部的框。

1. 选择**添加**将该项添加到项目。

## <a name="see-also"></a>请参阅

- [创建工作流项目](../workflow-designer/creating-a-workflow-project.md)