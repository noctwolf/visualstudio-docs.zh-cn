---
title: Blend for Visual Studio 功能导览
titleSuffix: ''
ms.date: 07/17/2017
ms.topic: conceptual
f1_keywords:
- Blend.Start.Dev12
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2651a5fc2c32de5018e8fa07f42c5067d469758c
ms.sourcegitcommit: 51dad3e11d7580567673e0d426ab3b0a17584319
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2019
ms.locfileid: "66820569"
---
# <a name="blend-for-visual-studio-overview"></a>Blend for Visual Studio 概述

Blend for Visual Studio 可用于设计基于 XAML 的 Windows 和 Web 应用程序。 它提供了与 Visual studio 相同的基本 XAML 设计体验，并添加了可视化设计器，以用于高级任务，例如动画和行为。 有关 Blend 和 Visual Studio 之间的比较，请参阅[在 Visual Studio 和 Blend for Visual Studio 中设计 XAML](../designers/designing-xaml-in-visual-studio.md)。

Blend for Visual Studio 是 Visual Studio 的一个组件。 若要安装 Blend，请在 Visual Studio 安装程序  中，选择“通用 Windows 平台开发”  或“.NET 桌面开发”  工作负载。 这两种工作负载均包括 Blend for Visual Studio 组件。

![UWP 工作负载组件](media/installer-uwp.png)&nbsp;&nbsp;&nbsp;&nbsp;![.NET 桌面开发工作负载组件](media/installer-dotnet-desktop.png)

如果是初次接触 Blend for Visual Studio，则要花一些时间来熟悉工作区的特有功能。 本主题将作用快速教程。

> [!NOTE]
> 若要浏览共享的设计功能，例如美工板、“文档大纲”窗口和“设备”窗口，请参阅[使用 XAML 设计器创建 UI](../designers/creating-a-ui-by-using-xaml-designer-in-visual-studio.md)   。

## <a name="tools-panel"></a>“工具”面板

可在应用程序中通过 Blend for Visual Studio 的“工具”  面板创建和修改对象。 打开 .xaml 文件时，“工具”面板显示在 XAML 设计器的左侧   。

可以通过使用鼠标选择工具并在美工板上进行绘制来创建对象。

![Blend for Visual Studio 中的“工具”面板](../designers/media/blend5toolspanel.png)

> [!TIP]
> “工具”面板中的某些工具有变体（如图中的 A 到 F 所示）  。 要访问这些变体，请右键单击或单击并按住该工具。
>
> ![Blend for Visual Studio 中的形状工具变体](media/rectangle-shape-tool-blend.png)

|||||
|-|-|-|-|
|![选择工具](../designers/media/b1_1.png)|**选择工具** - 选择对象和路径。<br /><br /> 使用“直接选择”  工具可选择嵌套对象和路径段。|![标注 A](../designers/media/b5_label_a.png)|**渐变和画笔工具**|
|![视图工具](../designers/media/b1_2.png)|**视图工具** - 调整美工板的视图，例如平移和缩放。|![标注 B](../designers/media/b5_label_b.png)|**路径工具**|
|![画笔工具](../designers/media/b1_3.png)|**画笔工具** - 处理对象的可视特性，例如转换画笔、绘制对象，或者选择某对象属性将其应用到其他对象。|![标注 C](../designers/media/b5_label_c.png)|**形状工具**|
|![对象工具](../designers/media/b1_4.png)|**对象工具** - 在美工板上绘制最常用的对象，例如路径、形状、布局面板、文本和控件。|![标注 D](../designers/media/b5_label_d.png)|**版式面板**|
|![资产工具](../designers/media/b1_5.png)|**资产工具** - 访问“资产”  面板并显示库中最近用过的资产。|![标注 E](../designers/media/b5_label_e.png)|**文本控件**|
|||![标注 F](../designers/media/b5_label_f.png)|**常见控件**|

## <a name="assets-window"></a>“资产”窗口

“资产”窗口包含所有可用控件，类似于 Visual Studio 中的“工具箱”   。 除控件外，“资产”  窗口还包括所有可添加到美工板的内容，例如样式、媒体、行为和效果等。 要打开“资产”窗口，请选择“视图” > “资产窗口”或按 Ctrl+Alt+X       。

![Blend for Visual Studio 中的“资产”窗口](../designers/media/blend5_assets_panel.png)

|||
|-|-|
|![“资产”搜索框](../designers/media/b1_1.png)|**搜索框** - 可在“搜索”  框中键入值来筛选资产列表。|
|![网格模式和列表模式](../designers/media/b1_2.png)|**网格模式和列表模式** - 在资产的“网格模式”  视图和“列表模式”  视图之间切换。|
|![资产类别](../designers/media/b1_3.png)|**资产类别** - 单击类别或子类别查看该类别中资产的列表。|
|![样式](../designers/media/b1_4.png)|**样式** - 显示资源字典中包含的所有样式。|
|![说明](../designers/media/b1_5.png)|**说明** - 查看所选资产类别或子类别的说明。|

## <a name="objects-and-timeline-window"></a>“对象和时间线”窗口

使用此窗口可在美工板上组织对象以及（如果需要）对它们进行动画处理。 要打开“对象和时间线”窗口，请选择“视图” > “对象和时间线”或按 Ctrl+W、U       。

![动画模式下的“对象和时间线”窗口](../designers/media/b5_object_timeline_animation.png)

|||
|-|-|
|![对象视图](../designers/media/b1_1.png)|**对象视图** - 查看文档的可视树。 可以深化到不同级别的详细信息。 还可以添加层以便进一步在美工板上组织对象。 通过这种方式可以将它们作为组进行锁定和隐藏。|
|![记录模式指示器](../designers/media/b1_2.png)|记录模式指示器  - 查看是否在时间线中记录属性更改。|
|![情节提要选取器](../designers/media/b1_3.png)|情节提要选取器  - 查看已创建的情节提要的列表。|
|![关闭情节提要](../designers/media/b1_4.png)|**关闭情节提要** - 关闭当前情节提要。|
|![情节提要选项](../designers/media/b1_5.png)|**情节提要选项** - 创建、复制、反向、删除、重命名或关闭情节提要。|
|![播放控件](../designers/media/b1_6.png)|**播放控件** - 在时间线中导航。 也可拖动播放指针来定位（或*推移*）时间线。|
|![返回到范围](../designers/media/b1_7.png)|**返回到范围** - 将对象视图的范围返回到上一个根对象或上一个范围。 仅当修改样式或模板时，才能执行此操作。|
|![记录关键帧](../designers/media/b1_8.png)|**记录关键帧** - 记录所选对象属性在当前时间点的快照。|
|![对齐选项](../designers/media/b1_9.png)|**对齐选项** - 设置时间线对齐、对齐分辨率以及关闭时间线对齐。|
|![显示 隐藏 锁定 解除锁定](../designers/media/97fa60b9-0caf-4387-9225-b57510d32209.png)|**显示/隐藏**、**锁定/解除锁定** - 显示或隐藏对象视图的可见性和锁定选项。|
|![播放指针在时间线上的位置](../designers/media/b1_11.png)|**播放指针在时间线上的位置** - 以毫秒为单位显示当前时间。 也可以直接在此字段中输入时间值以跳到特定的时间点。 精度取决于“对齐选项”  中设置的对齐分辨率。|
|![播放指针](../designers/media/b1_12.png)|**播放指针** - 确定动画所处的时间点。 可以在时间线中拖动播放指针，以便预览动画。|
|![时间线上设置的关键帧](../designers/media/b1_13.png)|**时间线上设置的关键帧** - 更改特点时间点的属性值。|
|![更改对象顺序](../designers/media/d839d12c-07a1-4127-a830-4a8e7069f4fe.png)|**更改对象顺序** - 设置对象的显示顺序。 单击此按钮可在结构视图中按 Z 顺序（从前到后）或按标记顺序（在“XAML”  视图中出现的顺序）排列对象。|
|![时间线缩放](../designers/media/b1_15.png)|**时间线缩放** - 设置时间线的缩放分辨率。 通过放大，可以编辑动画的更多细节；而通过缩小，可更全面地显示在更长时间段内发生的情况。 如果进行放大，但无法在所需时间位置设置关键帧，请验证设置的对齐分辨率是否足够高。|
|![标注 16](../designers/media/b5_label_16.png)|**时间线构成区域** - 查看时间线，并通过拖动关键帧或通过其快捷菜单移动关键帧。|

## <a name="properties-window"></a>“属性”窗口

使用此窗口可查看和修改对象的属性。 还可以直接在美工板上设置它们。 若如此操作，则“属性”  窗口中会反映出属性更改。 要打开“属性”窗口，请选择“视图” > “属性窗口”，或按 Ctrl+W、P       。

![Blend for Visual Studio 中的“属性”窗口](../designers/media/blend5_properties_panel.png)

**类别** - 展开和折叠类别的属性。 单击“展开”![展开](../designers/media/6375953d-074c-421a-bbb3-6f5055b67b64.png)和“折叠”![折叠](../designers/media/b5_collapse_button.png)以显示或隐藏类别详细信息   。

|||
|-|-|
|![名称和类型](../designers/media/b1_1.png)|**名称和类型** - 查看所选对象的图标、名称和类型。|
|![排列依据](../designers/media/b1_2.png)|**排列方式** - 按名称、源或类别的字母顺序排列属性。|
|![画笔属性](../designers/media/b1_3.png)|**画笔属性** - 设置填充画笔、笔划画笔和前景画笔等画笔的可视属性。|
|![颜色编辑器](../designers/media/b1_4.png)|**颜色编辑器** - 用于纯色画笔和渐变画笔。|
|![颜色选取器](../designers/media/b1_5.png)|**颜色选取器** - 选择颜色。|
|![色卡](../designers/media/b1_6.png)|**色卡** - 查看初始颜色、当前颜色和上一种颜色|
|![取色器](../designers/media/b1_7.png)|**取色器** - 使用屏幕上任意元素的颜色。 选择“纯色画笔”  时，“颜色取色器”  可用。 选择“渐变画笔”  时，“渐变取色器”  可用。|
|![属性和事件](../designers/media/b1_8.png)|**属性和事件** - 为所选元素设置属性或选择事件。|
|![搜索框](../designers/media/b1_9.png)|**搜索框** - 搜索属性。 在“搜索”  框中键入值来筛选显示的属性。|
|![画笔编辑器选项卡](../designers/media/97fa60b9-0caf-4387-9225-b57510d32209.png)|**画笔编辑器选项卡** - 用于选择画笔编辑器。 可选择“无画笔”  、“纯色画笔”  、“渐变画笔”  、“平铺画笔”  或“画笔资源”  。|
|![颜色资源](../designers/media/b1_11.png)|**颜色资源** - 将完全相同的颜色应用于不同属性。 “颜色资源”  选项卡包括“本地资源”  和“系统资源”  。|
|![RGB 颜色空间](../designers/media/b1_12.png)|**RGB 颜色空间**- 通过调整“R”  、“G”  或“B”  （分别表示红、绿、蓝）数字编辑器中的值修改颜色。|
|![Alpha 通道](../designers/media/b1_13.png)|**Alpha 通道** - 使用 **A** 旁边的数字编辑器修改 Alpha 值。|
|![将颜色转换为资源](../designers/media/d839d12c-07a1-4127-a830-4a8e7069f4fe.png)|**将颜色转换为资源** - 将所选颜色转换为颜色资源。 在单击“颜色资源”选项卡时，可以获得颜色资源。|
|![颜色十六进制值](../designers/media/b1_15.png)|**十六进制值** - 查看所显示颜色的十六进制值。|
|![标注 16](../designers/media/b5_label_16.png)|**渐变滑块** - 仅当选择渐变画笔时才显示。|
|![显示高级属性](../designers/media/d50027a1-6824-4ad8-8b4e-558b0756dcf8.png)|**显示高级属性** - 查看不常用属性的类别。|

## <a name="see-also"></a>请参阅

- [插入控件并修改其行为](../designers/insert-controls-and-modify-their-behavior-in-xaml-designer.md)
- [动态显示对象](../designers/animate-objects-in-xaml-designer.md)
- [绘制形状和路径](../designers/draw-shapes-and-paths.md)
- [在 Visual Studio 和 Blend for Visual Studio 中设计 XAML](../designers/designing-xaml-in-visual-studio.md)
