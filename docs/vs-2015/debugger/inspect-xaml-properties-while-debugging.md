---
title: 在调试时检查 XAML 属性 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 390edde4-7b8d-4c89-8d69-55106b7e6b11
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a30f04c3d2b2d109816ff8bcfbf17fe483f24886
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51758862"
---
# <a name="inspect-xaml-properties-while-debugging"></a>在调试时检查 XAML 属性
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

可以获取与你正在运行的 XAML 代码的实时视图**实时可视化树**并**实时属性资源管理器**。 这些工具为你提供了正在运行的 XAML 应用程序的 UI 元素的树视图，并显示你选择的任何 UI 元素的运行时属性。  
  
 可以在下列配置中使用这些工具：  
  
|应用类型|操作系统和工具|  
|-----------------|--------------------------------|  
|Windows Presentation Foundation（4.0 和更高版本）应用程序|Windows 7 和更高版本|  
|Windows 应用商店和 Windows Phone 8.1 应用|Windows 10 及更高版本，与[Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)|  
|通用 Windows 应用|Windows 10 及更高版本，与[Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)|  
  
## <a name="looking-at-elements-in-the-live-visual-tree"></a>查看实时可视化树中的元素  
 让我们开始使用具有列表视图和一个按钮的非常简单的 WPF 应用程序。 每次单击按钮时，另一个项将添加到列表中。 偶数项以灰色显示，奇数项以黄色显示。  
  
 创建新 C# WPF 应用程序（“文件”/“新建”/“项目”，然后选择 C# 并查找 WPF 应用程序）。 其命名为**TestXAML**。  
  
 将 MainWindow.xaml 更改为以下内容：  
  
```xaml  
<Window x:Class="WpfApplication1.MainWindow"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    xmlns:local="clr-namespace:WpfApplication1"  
    mc:Ignorable="d"  
     Title="MainWindow" Height="350" Width="525">  
    <Grid>  
        <Button x:Name="button" Background="LightBlue" Content="Add Item" HorizontalAlignment="Left" Margin="216,206,0,0" VerticalAlignment="Top" Width="75" Click="button_Click"/>  
        <ListBox x:Name="listBox" HorizontalAlignment="Left" Height="100" VerticalAlignment="Top" Width="100" Margin="205,80,0,0"/>  
    </Grid>  
</Window>  
```  
  
 将下面的命令处理程序添加到 MainWindow.xaml.cs 文件中：  
  
```csharp  
private void button_Click(object sender, RoutedEventArgs e)  
{  
    ListBoxItem item = new ListBoxItem();  
    item.Content = "Item" + ++count;  
    if (count % 2 == 0)  
    {  
        item.Background = Brushes.LightGray;  
    }  
    else  
    {  
        item.Background = Brushes.LightYellow;  
    }  
    listBox.Items.Add(item);  
}  
```  
  
 生成项目并启动调试。 （生成配置必须为“调试”，而不是“发布”。 有关生成配置的详细信息，请参阅[了解生成配置](../ide/understanding-build-configurations.md)。)  
  
 当窗口启动后，单击**添加项**按钮几次。 将显示如下所示的内容：  
  
 ![应用程序的主窗口](../debugger/media/livevisualtree-app.png "LiveVIsualTree 应用")  
  
 现在，打开**实时可视化树**窗口 (**调试 / Windows / 实时可视化树**，或沿 IDE 左侧查找它)。 将其拖离其停靠位置，以便我们可以看看此窗口并**Live 属性**窗口并排显示。 在中**实时可视化树**窗口中，展开**ContentPresenter**节点。 它应包含按钮和列表框的节点。 展开该列表框 (然后**ScrollContentPresenter**并**ItemsPresenter**) 以查找列表框项。 该窗口应如下所示：  
  
 ![实时可视化树中的 Listboxitem](../debugger/media/livevisualtree-listboxitems.png "LiveVisualTree Listboxitem")  
  
 返回到应用程序窗口并再添加几个项。 你应看到多个列表框项显示在**实时可视化树**。  
  
 现在让我们看看其中一个列表框项的属性。 第一个列表框中选择项**实时可视化树**然后单击**显示属性**工具栏上的图标。 **实时属性资源管理器**应显示。 请注意，**内容**字段是"Item1"，并**背景**字段是 **#ffffffe0** （浅黄色）。 返回到**实时可视化树**，然后选择第二个列表框项。 **实时属性资源管理器**应显示**内容**字段是"Item2"，并**后台**字段是 **#ffd3d3d3** （浅灰色).  
  
 XAML 的实际结构具有大量你可能并不直接感兴趣的元素，并且如果你不熟悉代码，就可能很难导航树以查找你正在寻找的内容。 因此**实时可视化树**有两种方法，可用于使用应用程序的 UI 来帮助你找到你想要检查的元素。  
  
 **在运行的应用程序中启用选择**。 选中最左侧的按钮上时，可以启用此模式**实时可视化树**工具栏。 在此模式下，可以在应用程序中，选择 UI 元素和**实时可视化树**(与**实时属性查看器**) 会自动更新以显示在树中与该元素对应的节点和其属性。  
  
 **在运行的应用程序中显示布局装饰器**。 当选择“启用选择”按钮右侧紧靠的按钮时，可以启用此模式。 当**显示布局装饰器**处于启用状态，它会导致应用程序窗口，显示所选对象的边界沿水平和垂直行，以便您可以看到它与什么对齐，以及显示边距的矩形。 例如，将同时**启用所选内容**并**显示布局**，然后选择**添加项**应用程序中的文本块。 你应看到中的文本块节点**实时可视化树**的文本块的属性和**实时属性查看器**，以及文本块的边界上的水平和垂直线条。  
  
 ![Displaylayout 中的 Livepropertyviewer](../debugger/media/livevisualtreelivepropertyviewer-displaylayout.png "LiveVisualTreeLivePropertyViewer DisplayLayout")  
  
 **预览所选内容**。 你可以通过选择“实时可视化树”工具栏上从左侧起第三个按钮来启用此模式。 如果你有访问该应用程序的源代码的权限，则此模式将在声明元素处显示 XAML。 选择**启用所选内容**并**预览所选内容**，然后在测试应用程序中选择的按钮。 MainWindow.xaml 文件在 Visual Studio 中打开并且光标放置在定义按钮的行上。  
  
## <a name="using-xaml-tools-with-running-applications"></a>将 XAML 工具用于运行的应用程序  
 即使在没有源代码时，你也可以使用这些 XAML 工具。 当你附加到正在运行的 XAML 应用程序时，可以使用**实时可视化树**该应用程序的 UI 元素上过。 下面是一个示例，使用与我们之前使用的相同的 WPF 测试应用程序。  
  
1.  启动**TestXaml**中发布配置应用程序。 不能附加到正在运行的进程**调试**配置。  
  
2.  打开 Visual Studio 的第二个实例，然后单击**调试 / 附加到进程**。 查找**TestXaml.exe**可用进程，然后单击列表中**附加**。  
  
3.  则应用程序开始运行。  
  
4.  在 Visual Studio 的第二个实例中，打开**实时可视化树**(**调试 / Windows / 实时可视化树**)。 应会看到**TestXaml** UI 元素，并且您应该能够对其进行处理，未在直接调试应用程序。



