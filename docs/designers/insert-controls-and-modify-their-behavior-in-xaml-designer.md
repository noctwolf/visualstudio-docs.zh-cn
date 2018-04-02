---
title: 在 XAML 设计器中插入控件并修改其行为 | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: article
ms.assetid: a80fff74-bf01-41c9-ab85-ada7a873c3a9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- uwp
ms.openlocfilehash: 828b02daaed0b33bfa2f53cf16bee9b60be2f939
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="insert-controls-and-modify-their-behavior-in-xaml-designer"></a>在 XAML 设计器中插入控件并修改其行为

控件使用户能够与你的应用进行交互。 可以使用它们收集信息并执行操作（如对对象进行动画处理或查询数据源）。

## <a name="add-controls-to-the-artboard"></a>向美工板添加控件

可以将控件从“资产”  面板拖到“美工板” ，然后在“属性”  窗口中进行修改。

![Blend - 资产 - FlipView](../designers/media/blend_assetsflipview_xaml.png "blend_AssetsFlipView_XAML")

这些视频向你演示如何使用一些更常用的控件。

|控件|观看简短视频|
|-------------|-------------------------|
|`Menu` ![](../designers/media/015a263c-0b2b-4253-ac57-b86fcb8c9591.png)|![播放图标](../designers/media/bldadminconsoleinitialconfigicon.PNG)[添加控件](https://www.youtube.com/watch?v=ra4AHfgD4Ys&list=PLBDF977B2F1DAB358&index=45)|
|`Button` ![](../designers/media/05df1779-a68f-436b-b834-a91b7995a3ec.png)|![播放图标](../designers/media/bldadminconsoleinitialconfigicon.PNG)[设计按钮](http://www.popscreen.com/v/6A4gb/Microsoft-Expression-Blend-Designing-a-Button)|
|`Textblock` ![](../designers/media/42165963-00f7-4a33-abcd-b0849edebada.png)|![播放图标](../designers/media/bldadminconsoleinitialconfigicon.PNG)[将图像添加到文本块](http://www.popscreen.com/v/6A4du/Microsoft-Expression-Blend-Adding-Images-to-a-TextBlock)|
|`Slider` ![](../designers/media/bf689d92-3c74-4218-815c-e98c930ac189.png)|![播放图标](../designers/media/bldadminconsoleinitialconfigicon.PNG)[生成带工具提示的滑块](http://www.bing.com/videos/search?q=slider%20expression%20blend&qs=n&form=QBVR&pq=slider%20expression%20blend&sc=1-23&sp=-1&sk=#view=detail&mid=F1BB7DB91B2772A8CA2AF1BB7DB91B2772A8CA2A)|

### <a name="make-a-control-out-of-an-image-shape-or-path"></a>使用图像、形状或路径创建控件

 可以使任何对象都成为控件。

 ![Blend“构成控件”对话框](../designers/media/blend_makeintocontrol_xaml.png "blend_MakeIntoControl_XAML")

 例如，假设页面中心的电视的图片。 可以使用类似于电视按钮的小图像创建控件。 然后，用户可以单击这些按钮以更改频道。

 可以这样做的原因是因为这些按钮现在是控件。 借助控件，可以响应用户交互；在此例中是当用户单击按钮时。

 若要创建控件，请选择对象。 然后在“工具”  菜单上，单击“创建控件” 。

## <a name="make-controls-do-things"></a>使控件执行操作

 控件可以在用户与之交互时执行操作。 例如，这些操作可以启动动画、更新数据源或播放视频。

 使用 *触发器*、 *行为*和 *事件* 可使控件执行操作。

### <a name="triggers"></a>触发器

 *触发器* 更改属性或执行任务以响应事件或另一个属性中的更改。 例如，可以在用户将鼠标指针悬停在按钮上方时更改按钮的颜色。

 ![“触发器”面板](../designers/media/custom_button_blend_propertytriggerinfo.png)

 **观看简短视频：**![播放图标](../designers/media/bldadminconsoleinitialconfigicon.PNG)[属性触发器](http://www.popscreen.com/v/6A4gO/Microsoft-Expression-Blend-Adding-a-Property-Trigger)。

### <a name="behaviors"></a>行为

 *行为* 是可重复重用的代码包。 它发挥的作用比更改属性稍微多一点。 它可以执行操作，例如查询数据服务。 Blend 附带了连A小型集合，但可以添加更多。 将行为拖动到到你美工板中的任何对象，然后通过设置属性来自定义行为。

 ![“属性”面板中的 FluidMoveBehavior](../designers/media/b4_fluidmovebehaviorproperties_sample.png)

 **观看简短视频：**![播放图标](../designers/media/bldadminconsoleinitialconfigicon.PNG)[混合提示：使用行为简介的第 1 部分](http://www.bing.com/videos/search?q=Expression%20blend%20behaviors&qs=n&form=QBVR&pq=expression%20blend%20behavior&sc=4-25&sp=-1&sk=#view=detail&mid=CF0DD797ED84DE740904CF0DD797ED84DE740904)。

### <a name="events"></a>事件

 最获得最佳灵活性，请处理 *事件*。 必须编写一些代码。

 **观看简短视频：**![播放图标](../designers/media/bldadminconsoleinitialconfigicon.PNG)[添加鼠标事件](https://www.youtube.com/watch?v=2PMxAlb-x_E)。