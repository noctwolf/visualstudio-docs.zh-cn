---
title: 在 XAML 设计器中插入控件并修改其行为
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: a80fff74-bf01-41c9-ab85-ada7a873c3a9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: c50e0dd1884a588c95cd4baa4c544d67a85989b8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53911476"
---
# <a name="insert-controls-and-modify-their-behavior-in-xaml-designer"></a>在 XAML 设计器中插入控件并修改其行为

控件使用户能够与你的应用进行交互。 可以使用它们收集信息并执行操作（如对对象进行动画处理或查询数据源）。

## <a name="add-controls-to-the-artboard"></a>向美工板添加控件

可以将控件从“资产”  面板拖到“美工板” ，然后在“属性”  窗口中进行修改。

![Blend 资产选项卡控件](../designers/media/blend_assetsflipview_xaml.png)

### <a name="make-a-control-out-of-an-image-shape-or-path"></a>使用图像、形状或路径创建控件

可以使任何对象都成为控件。

![Blend“构成控件”对话框](../designers/media/blend_makeintocontrol_xaml.png)

例如，假设页面中心的电视的图片。 可以使用类似于电视按钮的小图像创建控件。 然后，用户可以单击这些按钮以更改频道。

可以这样做的原因是因为这些按钮现在是控件。 借助控件，可以响应用户交互；在此例中是当用户单击按钮时。

若要创建控件，请选择对象。 然后在“工具”  菜单上，单击“创建控件” 。

## <a name="make-controls-do-things"></a>使控件执行操作

控件可以在用户与之交互时执行操作。 例如，这些操作可以启动动画、更新数据源或播放视频。

使用 *触发器*、 *行为*和 *事件* 可使控件执行操作。

### <a name="triggers"></a>触发器

*触发器* 更改属性或执行任务以响应事件或另一个属性中的更改。 例如，可以在用户将鼠标指针悬停在按钮上方时更改按钮的颜色。

![“触发器”面板](../designers/media/custom_button_blend_propertytriggerinfo.png)

### <a name="behaviors"></a>行为

*行为* 是可重复重用的代码包。 它发挥的作用比更改属性稍微多一点。 它可以执行操作，例如查询数据服务。 Blend 附带了小型行为集合，但可以添加更多。 将行为拖动到到你美工板中的任何对象，然后通过设置属性来自定义行为。

![“属性”面板中的 FluidMoveBehavior](../designers/media/b4_fluidmovebehaviorproperties_sample.png)

**观看视频：**![播放图标](../designers/media/bldadminconsoleinitialconfigicon.PNG) [Blend 提示：使用行为简介第 1 部分](http://www.bing.com/videos/search?q=Expression%20blend%20behaviors&qs=n&form=QBVR&pq=expression%20blend%20behavior&sc=4-25&sp=-1&sk=#view=detail&mid=CF0DD797ED84DE740904CF0DD797ED84DE740904)。

### <a name="events"></a>事件

最获得最佳灵活性，请处理 *事件*。 必须编写一些代码。