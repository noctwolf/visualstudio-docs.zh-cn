---
title: 工作流设计器-如何： 在工作流中设置断点
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
ms.assetid: e41b21c9-c061-4358-8e2f-eb5e412864a8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d2ef863bfb899c218a65673236c284bed63aed11
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-set-breakpoints-in-workflows"></a>如何：在工作流中设置断点

当你使用 Windows 工作流设计器时，你可以在图形工作流上设置断点，像在 Visual Basic 或 C# 代码中一样。 正如所料，工作流执行将在设置的每个断点处停止。

 断点具有三种状态：*挂起*，*绑定*，和*错误*。 当您设置断点时，断点处于“挂起”状态，并且由一个实心的红色图标表示。 当运行时加载了工作流类型后，断点将成为“绑定”状态。 如果为断点指定了不正确的格式（例如无效的活动名称），则会显示一个错误窗口。 断点仍然会添加到断点窗口，但标有一个小“x”。

> [!NOTE]
> 不支持在调用的工作流上设置断点。

> [!WARNING]
> 确保选择选项**启用 ' 仅我代码 （仅限托管）**从**工具**，**选项**，**调试**之前的菜单调试。 如果你有另一个序列中嵌套的两个序列并且在第一个内部序列上设置一个断点，按**F11**不将其如果调试到第二个内部序列**启用 ' 仅我代码 （仅限托管）**未选择选项。

> [!WARNING]
> 如果 XAML 文件属性的完整路径不准确，将不命中工作流中的断点。在将项目/解决方案移到另一个文件夹或另一台计算机后，XAML 文件的完整路径不准确。选择 Ctrl + S 可保存和更新完整路径属性。

## <a name="to-set-a-breakpoint-on-an-activity-in-the-design-view"></a>在设计视图中的活动上设置断点

1.  选择希望调试器在其上中断的活动。

2.  上**调试**菜单上，选择**切换断点**。 此时将在该活动的左上边缘显示一个红色图标。

     或者，也可以按快捷键**F9**密钥之后选择活动或你可以右键单击该活动并选择**断点**然后**插入断点**从上下文菜单。

## <a name="see-also"></a>请参阅

- [如何：调用工作流调试器](../workflow-designer/how-to-invoke-the-workflow-debugger.md)
- [使用工作流设计器调试工作流](../workflow-designer/debugging-workflows-with-the-workflow-designer.md)
- [如何：使用工作流设计器调试 XAML](../workflow-designer/how-to-debug-xaml-with-the-workflow-designer.md)