---
title: 如何：仅使用键盘进行操作
description: 了解如何使用默认快捷键组合在 Visual Studio 集成开发环境 (IDE) 中轻松导航和编码。
ms.date: 05/10/2019
ms.topic: conceptual
helpviewer_keywords:
- Toolbox, shortcut keys
- shortcut keys [Visual Studio]
- windows [Visual Studio], accessibility
- dialog boxes [Visual Studio], shortcut keys
- keyboard shortcuts [Visual Studio]
- accessibility [Visual Studio]
ms.assetid: d71a4cc1-d352-4164-8538-3f9fa070a331
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5a8759643b9cf72cac671a8d733e1306760afc36
ms.sourcegitcommit: 614d5b99576ea27a41957cd94062dc95cbd29c1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531602"
---
# <a name="how-to-use-the-keyboard-exclusively"></a>如何：仅使用键盘进行操作

键盘快捷方式可以更轻松地导航 Visual Studio IDE 和编码。 我们将讨论键盘快捷方式的一些高效使用方法。

有关 Visual Studio 中的完整快捷键列表，请参阅[默认键盘快捷方式](../../ide/default-keyboard-shortcuts-in-visual-studio.md)。 有关其他 Microsoft 产品可用的键盘快捷方式的信息，请参阅 [https://www.microsoft.com/accessibility/](http://go.microsoft.com/fwlink/?LinkID=40400)。

::: moniker range="vs-2017"

> [!TIP]
> 要详细了解辅助功能更新，请参阅博客文章 [Visual Studio 2017 版本 15.3 中的辅助功能改进](https://devblogs.microsoft.com/visualstudio/accessibility-improvements-in-visual-studio-2017-version-15-3/)。

::: moniker-end

> [!NOTE]
> 根据所使用的设置或 Visual Studio 版本，看到的对话框和菜单命令可能与“帮助”中描述的有所不同。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[重置设置](../environment-settings.md#reset-settings)。

## <a name="toolbox-controls"></a>工具箱控件

可以使用键盘将工具箱上的控件添加到窗体或设计器中。

### <a name="to-add-controls-from-the-toolbox-to-a-designer-from-the-keyboard"></a>使用键盘将工具箱中的控件添加到设计器中

1. 在菜单栏上，依次选择“视图” > “工具箱”。

2. 使用“Ctrl+向上键”或“Ctrl+向下键”键盘快捷方式，在“工具箱”选项卡的各部分间移动。

3. 使用向上键或向下键，在控件之间移动。

4. 选中控件后，使用 Enter 键。

   Visual Studio 将控件添加到窗体或设计器。

## <a name="dialog-box-options"></a>对话框选项

 使用键盘，可以在对话框中的选项间移动并更改选项设置。

### <a name="to-set-dialog-box-options-from-the-keyboard"></a>使用键盘设置对话框选项

1. 使用 Tab 或 Shift+Tab，在对话框中的控件间上下移动。

2. 更改选项设置：

    - 对于单选按钮，请使用向上键和向下键更改所选内容。

    - 对于复选框，请使用空格键来选中或取消选中。

    - 对于下拉列表，请使用“Alt+向下键”来显示项，然后使用向上键和向下键更改选定的项。

    - 对于按钮，选择 Enter 可激活。

    - 对于网格，请使用箭头键来导航。 对于网格中的下拉列表，请使用 Shift + Alt + 向下键来显示项，然后使用向上键和向下键更改选定的项。

## <a name="window-and-file-navigation"></a>窗口和文件导航

通过几种方法，可以使用键盘在打开的工具和文档窗口之间移动。 也可以使用键盘来移动工具窗口并将其停靠在不同的位置。

### <a name="to-navigate-among-windows-and-files-in-the-ide-from-the-keyboard"></a>使用键盘在 IDE 的窗口和文件间导航

- 要在编辑器或设计器中的文件间移动，请选择 Ctrl+Tab 键盘快捷方式以显示 IDE 导航器，并选中“活动文件”。 选择 Enter 键，导航到突出显示的文件。

- 若要在停靠的工具窗口间移动，请选择 Alt+F7 键盘快捷方式以显示 IDE 导航器，并选中“活动工具窗口”。 选择 Enter 键，导航到突出显示的窗口。

### <a name="to-move-and-dock-tool-windows-from-the-keyboard"></a>通过键盘移动和停靠工具窗口

1. 导航到要移动的工具窗口，并将焦点置于该窗口。

2. 在“窗口”菜单上，选择“可停靠”选项。

3. 使用 Alt+空格键键盘快捷方式，然后选择“移动”。

     随即显示停靠菱形引导标记。

4. 使用箭头键将窗口移动到新位置。

     使用箭头键时，鼠标指针会随窗口移动。

5. 到达新位置后，使用箭头键将鼠标指针移到菱形引导标记的正确部位。

     新的停靠位置便出现工具窗口的边框。

6. 选择 Enter。

     工具窗口随即进入新的停靠位置。

## <a name="see-also"></a>请参阅

* [标识并自定义键盘快捷键](../../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md)
* [辅助功能提示和技巧](../../ide/reference/accessibility-tips-and-tricks.md)
* [默认键盘快捷方式](../../ide/default-keyboard-shortcuts-in-visual-studio.md)
