---
title: 使用旧版工作流设计器
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- Visual Studio 2005 Extensions for Windows Workflow Foundation, about
ms.assetid: 7af53077-afd7-465f-9c1d-b387e9d4f216
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 794b52c918eb727fe67d24af209d21403da18475
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31975463"
---
# <a name="using-the-legacy-workflow-designer"></a>使用旧版工作流设计器

通过 Visual Studio 2010 的旧工作流设计器提供可用于面向.NET Framework 版本 3.5 或 WinFX。

它可通过选择 **.NET Framework 3.0**选项或 **.NET Framework 3.5**的下拉列表的顶部列表中的选项**新项目**窗口。 Visual Studio 2010 中的默认选项才 **.NET Framework 4**用于创建面向.NET Framework 4 的 Windows Workflow Foundation (WF) 应用程序。

工作流设计器使您能够以图形方式创建使用熟悉的 Visual Studio 用户界面的 Windows Workflow Foundation (WF) 应用程序。 Windows Workflow Foundation (WF) 应用程序由名为活动的工作流过程步骤组成。 若要创建工作流，构成活动设计图面上的，通过拖动其相应的活动设计器从**工具箱**拖到设计图面。

下表列出 Visual Studio for 各种 Windows Workflow Foundation 的主要的功能。

|功能|描述|
|-------------|-----------------|
|活动拖放|将活动从**工具箱**拖到设计图面来创建工作流。|
|属性浏览器|标准**属性**Visual Studio 窗口中的用于配置活动的属性。|
|缩放|双筒望远镜图标**缩放级别**图标位于设计图面右侧垂直滚动条的下方。 单击双筒望远镜图标并选择一个缩放百分比，以使工作流图形放大或缩小。你还可以使用**平移**图标放大镜光标选项来放大和缩小。|
|平移|**平移**图标，一个包含指向四个方向的十字的箭头的圆圈位于双筒望远镜缩放图标的下方的设计图面右侧垂直滚动条的下方。 如果单击平铺图标，一个弹出菜单将提供以下光标选项：<br /><br /> -**放大**放大镜光标允许您通过单击设计图面放大。<br />-**缩小**放大镜光标允许您通过单击设计图面缩小。<br />-**导航工具**手形光标允许您"抓住"并变换工作流设计图面中的视图。<br />-**默认**箭头光标允许您从其他光标切换回默认箭头光标。|
|自动滚动|如果工作流很大，您可能需要将活动放在超出设计图面区域可见显示部分的位置。 Visual Studio 允许你将接近你想要放置活动的设计图面边缘活动。 设计图面视图将在该方向上自动滚动。|
|智能标记|未完全配置或未有效配置的活动都标有感叹号图标。 可以单击该图标，查看活动上存在的配置需要的下拉列表。 然后，可以使用**属性**窗口来适当配置活动。 当所有属性对于活动均有效时，感叹号图标将消失。|

## <a name="see-also"></a>请参阅

- [开发工作流](http://go.microsoft.com/fwlink?LinkID=65010)