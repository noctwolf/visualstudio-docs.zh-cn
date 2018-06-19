---
title: 工作流设计器-如何： 将新项添加到工作流项目 （旧版）
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- sequential workflows, adding to workflow projects
- workflows, adding new items
- state machine workflows, adding to workflow projects
- activities, adding to workflow projects
ms.assetid: 130cd83d-942d-437b-bbb5-8088ec0a6d79
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6d6e9607f4924057568849fd7eabd4567130dc2f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31974230"
---
# <a name="how-to-add-a-new-item-to-a-workflow-project-legacy"></a>如何：向工作流项目添加新项（旧版）

创建使用 Visual Studio 2010 面向.NET Framework 版本 3.5 或 WinFX 提供的 Windows 工作流设计器的旧工作流项目后，你可以添加 Windows Workflow Foundation (WF) 项和其他熟悉的 Visual Studio到你的项目项。

下表列出了可添加到工作流项目中的 Windows Workflow Foundation 项。

|项|描述|
|----------|-----------------|
|Activity|活动定义在设计器代码文件中而用户代码在另一个代码文件中的活动。|
|Activity (具有单独的代码)|位于不同代码文件中的活动定义（以工作流标记形式表示）和用户代码。|
|顺序工作流 (代码)|工作流定义在设计器代码文件中而用户代码在另一个代码文件中的顺序工作流。|
|顺序工作流 (具有单独的代码)|工作流定义（以工作流标记形式表示）与用户代码位于不同代码文件中的顺序工作流。|
|状态机工作流 (代码)|工作流定义在设计器代码文件中而用户代码在另一个代码文件中的状态机工作流。|
|状态机工作流 (具有单独的代码)|工作流定义（以工作流标记形式表示）与用户代码位于不同代码文件中的状态机工作流。|

## <a name="to-add-a-new-item-to-a-workflow-project"></a>向工作流项目添加新项

1.  上**项目**菜单上，单击**添加新项**。

     **添加新项**对话框随即打开。

2.  选择一个项。

     前面的表列出了可用的 Windows Workflow Foundation 选择。

3.  单击**添加**将该项添加到工作流项目。

## <a name="see-also"></a>请参阅

- [创建旧版工作流项目](../workflow-designer/creating-legacy-workflow-projects.md)