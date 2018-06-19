---
title: 工作流设计器的顺序工作流视图 （旧版）
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- sequential workflow views
- sequential workflows, views
ms.assetid: 135f24b9-1b37-442b-9ef8-f0f2108a3212
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ce1217ea629ae0301b72b444161d61db4fe448b1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31976014"
---
# <a name="sequential-workflow-views-legacy"></a>顺序工作流视图（旧版）

Visual Studio 2010 提供了一个旧的 Windows 工作流设计器，可用于面向.NET Framework 版本 3.5 或 WinFX。

工作流设计器使您能够以图形方式创建使用熟悉的 Visual Studio 用户界面的 Windows Workflow Foundation (WF) 应用程序。 Windows Workflow Foundation (WF) 应用程序由名为活动的工作流过程步骤组成。 若要创建工作流，构成活动设计图面上的，通过拖动其相应的活动设计器从**工具箱**拖到设计图面。

当你创建一个顺序工作流，这是[SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040)，工作流的三个视图都可用。 这些视图是从可访问**工作流**菜单和设计图面上的上下文菜单。

下表列出了每个视图的名称和说明。

|菜单/选项卡选项|描述|
|----------------------|-----------------|
|**查看顺序工作流**|右键单击设计图面并选择**查看顺序工作流**从上下文菜单的选项，以显示**顺序工作流**视图，其中显示了基于活动的图形表示形式的顺序工作流。 或选择**查看顺序工作流**从**工作流**菜单。|
|**查看取消处理程序**|右键单击设计图面并选择**查看取消处理程序**从上下文菜单的选项，以显示**顺序工作流**查看，它显示[CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050)与工作流关联的活动。 或选择**查看取消处理程序**从**工作流**菜单。|
|**查看错误处理程序**|右键单击设计图面并选择**查看错误处理程序**从上下文菜单的选项，以显示**错误**查看，它显示[FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055)与工作流关联的活动。 或选择**查看错误处理程序**从**工作流**菜单。|

 有关类似视图的详细信息，请参阅[活动视图 （旧版）](../workflow-designer/activity-views-legacy.md)。

## <a name="see-also"></a>请参阅

- [活动视图（旧版）](../workflow-designer/activity-views-legacy.md)
- [创建旧版工作流项目](../workflow-designer/creating-legacy-workflow-projects.md)
- [工作流创作模式](http://go.microsoft.com/fwlink?LinkID=65014)