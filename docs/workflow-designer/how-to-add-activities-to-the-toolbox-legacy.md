---
title: 工作流设计器-如何： 将活动添加到工具箱 （旧版）
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- Toolbox, adding activities
- activities, adding to Toolbox
ms.assetid: b66ea29c-120b-40ba-8a61-c1c8240850fa
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 99a8e1cef2ff5ddd526133355c608fa5218573d1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-activities-to-the-toolbox-legacy"></a>如何：向工具箱添加活动（旧版）

在生成与旧的 Windows 工作流设计器面向.NET Framework 版本 3.5 或 WinFX 工作流解决方案时，可以将自定义活动添加到工作流项目并将其设计器置于**工具箱**为轻松访问。 你还可以直接添加活动**工具箱**从动态链接库 (DLL)。

## <a name="to-add-an-activity-to-the-toolbox-from-a-dll"></a>从 DLL 中将活动添加到工具箱

1.  右键单击工具箱窗口图面下的**Windows 工作流**，然后单击**选择项**。

2.  在**选择工具箱项**对话框中，单击**System.Activities 组件**选项卡上，并依次**浏览**从右下角的窗口。

3.  从包含要添加到的自定义活动的实现的文件目录中选择 DLL**工具箱**，然后单击**打开**。

4.  单击**确定**以完成将活动添加到工具箱。

## <a name="see-also"></a>请参阅

- [使用旧版活动设计器](../workflow-designer/using-the-legacy-activity-designer.md)
- [旧版工作流活动](../workflow-designer/legacy-workflow-activities.md)