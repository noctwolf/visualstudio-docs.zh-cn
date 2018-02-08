---
title: "演练：使用 C# 或 Visual Basic 创建简单应用程序 | Microsoft 文档"
ms.custom: 
ms.date: 10/03/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- VB
- CSharp
ms.assetid: f84339c7-d617-4f56-bfcd-af2215c347ba
caps.latest.revision: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: b33816e074cf63826c931bcda0978ebdb5bb8bbe
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2018
---
# <a name="walkthrough-create-a-simple-application-with-c-or-visual-basic"></a>演练：使用 C# 或 Visual Basic 创建简单应用程序
通过完成本演练，你将熟悉在使用 Visual Studio 开发应用程序时可使用的许多工具、对话框和设计器。 你将创建一个简单的“Hello, World”应用程序、设计 UI、添加代码并调试错误，还会了解如何在集成开发环境 (IDE) 中工作。
  
##  <a name="BKMK_ConfigureIDE"></a> 配置 IDE  
首次启动 Visual Studio 时，系统会提示你进行登录。 在本演练中，此步骤为可选步骤。 接下来可能会显示一个对话框，让你选择开发设置和颜色主题。 保留默认值，然后选择“启动 Visual Studio”。  

![“选择设置”对话框](../ide/media/exploreide-settings.png "exploreide-settings")
  
启动 Visual Studio 后，将看到工具窗口、菜单和工具栏，以及主窗口空间。 工具窗口停靠在应用程序窗口的左侧和右侧，其顶部有 **“快速启动”**、菜单栏和标准工具栏。 应用程序窗口的中心是 **“起始页”**。 当您加载解决方案或项目时，编辑器和设计器将显示在 **起始页** 的空间中。 开发应用程序时，大部分时间都将用在此中心区域。  
  
![应用了常规设置的 IDE](../ide/media/exploreide-idewithgeneralsettings.png "ExploreIDE IDEwithgeneralsettings")  
  
##  <a name="BKMK_CreateApp"></a> 创建简单的应用程序  
  
### <a name="create-the-project"></a>创建项目  
在 Visual Studio 中创建应用程序时，应首先创建项目和解决方案。 此示例将创建一个 Windows Presentation Foundation (WPF) 项目。  
  
#### <a name="to-create-the-wpf-project"></a>创建 WPF 项目  
  
1.  创建新项目。 在菜单栏上，依次选择“文件”、“新建”、“项目...”。  
  
     ![在菜单栏上，依次选择“文件”、“新建”、“项目”](../ide/media/exploreide-filenewproject.png "ExploreIDE-FileNewProject")  
  
2.  例如，通过在左窗格中选择“已安装”、“Visual C#”、“Windows 经典桌面”，然后选择中间窗格中的“WPF 应用”，从而选择 Visual Basic 或 Visual C# WPF 应用模板。  命名新项目对话框底部的项目 HelloWPFApp。  
  
     ![创建 C# WPF 项目，HelloWPFApp](../ide/media/exploreide-newprojectcsharp.png "ExploreIDE-NewProjectcsharp")  
  
Visual Studio 将创建 HelloWPFApp 项目和解决方案，“解决方案资源管理器”将显示各种文件。 WPF 设计器在拆分视图中显示 MainWindow.xaml 的设计视图和 XAML 视图。 您可以滑动拆分器，以显示任一视图的更多或更少部分。  您可以选择只查看可视化视图或 XAML 视图。 （有关详细信息，请参阅[面向 Windows 窗体开发人员的 WPF 设计器](http://msdn.microsoft.com/47ad0909-e89b-4996-b4ac-874d929f94ca)。）“解决方案资源管理器”中显示以下项：  
  
![已加载 HelloWPFApp 文件的解决方案资源管理器](../ide/media/exploreide-hellowpfappfiles.png "ExploreIDE-HelloWPFAppFiles")  
  
你可以在创建项目后进行自定义。 通过使用 **属性** 窗口（ **视图** 菜单上），您可以显示和更改应用程序中的项目项、控件和其他项的选项。  
  
#### <a name="to-change-the-name-of-mainwindowxaml"></a>更改 MainWindow.xaml 的名称  
为 MainWindow 指定更具体的名称。  

1. 在 **“解决方案资源管理器”**中，选择 MainWindow.xaml。 此时应看到“属性”窗口，如果没有，请选择“视图”菜单，然后再选择“属性窗口”项。  
2. 将 **“文件名称”** 属性更改为 `Greetings.xaml`。  
  
     ![突出显示文件名的“属性”窗口](../ide/media/exploreide-filenameinpropertieswindow.png "ExploreIDE FilenameinPropertiesWindow")  
  
     “解决方案资源管理器”显示文件的当前名称是 Greetings.xaml，而嵌套代码文件的当前名称是 Greetings.xaml.vb 或 Greetings.xaml.cs。 此代码文件嵌套在 .xaml 文件节点下，表明它们的关系十分紧密。  
  
### <a name="design-the-user-interface-ui"></a>设计用户界面 (UI)  
我们会将三种类型的控件添加至此应用程序：一个 TextBlock 控件、两个 RadioButton 控件和一个 Button 控件。  
  
#### <a name="to-add-a-textblock-control"></a>添加 TextBlock 控件  
  
1.  通过选择 **视图** 菜单和 **工具箱** 项打开 **工具箱** 窗口。  
  
2.  在“工具箱”中，展开“公共 WPF 控件”节点以查看 TextBlock 控件。  
  
     ![突出显示 TextBlock 控件的工具箱](../ide/media/exploreide-textblocktoolbox.png "ExploreIDE-TextBlockToolbox")  
  
3.  通过选择“TextBlock”项并将其拖到设计图面的窗口中，将 TextBlock 控件添加到设计图面中。 把控件居中到窗口的顶部附近。  
  
你的窗口应与下图类似：  
  
![Greetings 窗体上的 TextBlock 控件](../ide/media/exploreide-greetingswithtextblockonly.png "ExploreIDE GreetingswithTextblockonly")  
  
XAML 标记应类似于以下示例：  
  
```xaml  
<TextBlock HorizontalAlignment="Center" TextWrapping="Wrap" VerticalAlignment="Center" RenderTransformOrigin="4.08,2.312" Margin="237,57,221,238"><Run Text="TextBlock"/><InlineUIContainer><TextBlock TextWrapping="Wrap" Text="TextBlock"/>  
```  

#### <a name="to-customize-the-text-in-the-text-block"></a>自定义文本块中的文本  
  
1.  在 XAML 视图中，找到 TextBlock 的标记并更改 Text 属性：  

   ```xaml
   Text="Select a message option and then choose the Display button."
   ```  
  
2.  使 TextBlock 重新居中（若有必要），并通过按“Ctrl-s”或使用“文件”菜单项保存所做的更改。  
  
接下来，向窗体添加两个 [RadioButton](/dotnet/framework/wpf/controls/radiobutton) 控件。  
  
#### <a name="to-add-radio-buttons"></a>添加单选按钮  
  
1.  在“工具箱”中，查找“RadioButton”控件。  
  
     ![选定 RadioButton 控件的“工具箱”窗口](../ide/media/exploreide-radiobuttontoolbox.png "ExploreIDE-RadioButtonToolbox")  
  
2.  通过选择“RadioButton”项并将其拖到设计图面的窗口中，将两个 RadioButton 控件添加到设计图面中。 移动按钮（通过选择它们并使用箭头键），以便按钮并排显示在 TextBlock 控件下。  
  
     你的窗口应如下所示：  
  
     ![包含文本块和两个单选按钮的 Greetings 窗体](../ide/media/exploreide-greetingswithradiobuttons.png "ExploreIDE Greetingswithradiobuttons")  
  
3.  在左侧 RadioButton 控件的“属性”窗口中，将“名称”属性（位于“属性”窗口顶部）更改为“HelloButton”。  

     ![RadioButton 属性窗口](../ide/media/exploreide-buttonproperties.png "exploreide-buttonproperties")  
  
4.  在右侧 RadioButton 控件的“属性”窗口中，将“名称”属性更改为“GoodbyeButton”，然后保存更改。  
  
你现在可以为每个 RadioButton 控件添加显示文本。 以下程序将更新 RadioButton 控件的 **“内容”** 属性。  
  
#### <a name="to-add-display-text-for-each-radio-button"></a>添加每个单选按钮的显示文本  
  
1.  在设计界面上，通过在 HelloButton 上按鼠标右键打开 HelloButton 的快捷菜单，选择“编辑文本”，然后输入“Hello”。  
  
2.  在 GoodbyeButton 上按鼠标右键打开 GoodbyeButton 的快捷菜单，选择“编辑文本”，然后输入“Goodbye”。  

### <a name="to-set-a-radio-button-to-be-checked-by-default"></a>设置要默认选中的单选按钮  
在此步骤中，我们将设置要默认选中的 HelloButton，以便始终选择两个单选按钮中的一个。  

在 XAML 视图中，找到 HelloButton 的标记并添加“IsChecked”属性：

```xaml
IsChecked="True"
```  

最后添加的 UI 元素是 [Button](/dotnet/framework/wpf/controls/button) 控件。  
  
#### <a name="to-add-the-button-control"></a>添加 Button 控件  
  
1.  在“工具箱”中，找到“按钮”控件，然后通过将控件拖到设计视图的窗体中，将其添加到 RadioButton 控件下方的设计界面中。  
  
2.  在 XAML 视图中，将 Button 控件的“内容”值从 `Content="Button"` 更改为 `Content="Display"`，然后保存更改。  
  
     标记应与以下示例类似：  
     `<Button Content="Display" HorizontalAlignment="Left" VerticalAlignment="Top" Width="75" Margin="215,204,0,0"/>`  
  
     你的窗口应与下图类似。  
  
     ![包含控件标签的 Greetings 窗体](../ide/media/exploreide-greetingswithconrollabels.png "ExploreIDE-Greetingswithconrollabels")  
  
### <a name="add-code-to-the-display-button"></a>向显示按钮添加代码  
此应用程序运行时，用户选择单选按钮，再选择“显示” 按钮之后，会显示一个消息框。 选择 Hello 将显示一个消息框，选择 Goodbye 将显示另一个。 要创建此行为，需将代码添加到 Greetings.xaml.vb 或 Greetings.xaml.cs 中的 Button_Click 事件。  
  
#### <a name="add-code-to-display-message-boxes"></a>添加代码以显示消息框    
1.  在设计图面上，双击 **“显示”** 按钮。  
  
     此时将打开 Greetings.xaml.vb 或 Greetings.xaml.cs，光标则位于 Button_Click 事件上。 
  
    ```vb  
    Private Sub Button_Click_1(sender As Object, e As RoutedEventArgs)  
  
    End Sub  
    ```    
    ```csharp  
    private void Button_Click_1(object sender, RoutedEventArgs e)  
    {  
  
    }  
    ```  
  
2.  输入以下代码：  
  
    ```vb  
    If HelloButton.IsChecked = True Then  
        MessageBox.Show("Hello.")  
    ElseIf GoodbyeButton.IsChecked = True Then 
        MessageBox.Show("Goodbye.")  
    End If  
  
    ```    
    ```csharp  
    if (HelloButton.IsChecked == true)
    {
         MessageBox.Show("Hello.");
    }
    else if (GoodbyeButton.IsChecked == true)
    {
        MessageBox.Show("Goodbye.");
    }
    ```  
  
3.  保存应用程序。  
  
##  <a name="BKMK_DebugTest"></a> 调试并测试应用程序  
接下来将调试应用程序，查找错误并测试两个消息框是否正确显示。 下面的说明将告诉你如何构建和启动调试器，但以后可以阅读 [生成 WPF 应用程序 (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf) 和 [Debugging WPF](../debugger/debugging-wpf.md) 以获取有关详细信息。  
  
### <a name="find-and-fix-errors"></a>查找并修复错误  
在此步骤中将遇到之前因更改 MainWindow.xaml 文件的名称而引起的错误。  
  
#### <a name="to-start-debugging-and-find-the-error"></a>开始调试和查找错误  
  
1.  选择 **“调试”**-&gt; **“启动调试”**，启动调试器。  
  
     ![“调试”菜单上的“启动调试”命令](../ide/media/exploreide-startdebugging.png "ExploreIDE-StartDebugging")  
  
     将出现“中断模式”窗口，“输出”窗口指示“发生 IOException: 找不到资源 'mainwindow.xaml'”。  
  
2.  依次选择“调试”、“停止调试”，停止调试器。  
  
     ![“调试”菜单上的“停止调试”命令](../ide/media/exploreide-stopdebugging.png "ExploreIDE-StopDebugging")  
  
开始进行本演练时，我们将 Mainwindow.xaml 重命名为 Greetings.xaml，但是该代码仍然引用 Mainwindow.xaml 作为应用程序的启动 URI，因此该项目无法启动。  
  
#### <a name="to-specify-greetingsxaml-as-the-startup-uri"></a>将 Greetings.xaml 指定为启动 URI  
  
1.  在“解决方案资源管理器”中，打开 App.xaml 文件（在 C# 项目中）或 Application.xaml 文件（在 Visual Basic 项目中）。  
  
2.  将 `StartupUri="MainWindow.xaml"` 更改为 `StartupUri="Greetings.xaml"`，然后保存更改。  
  
再次启动调试程序 （按“F5”）。 你应看到应用程序的 Greetings 窗口。 现在关闭应用程序窗口，停止调试。  
  
### <a name="to-debug-with-breakpoints"></a>使用断点进行调试  
可通过添加一些断点，在调试期间测试代码。 可以通过选择“调试”->“切换断点”、通过在编辑器中想要添加断点的代码行旁边的左边距中单击或按“F9”来添加断点。  
  
#### <a name="to-add-breakpoints"></a>添加断点  
  
1.  打开 Greetings.xaml.vb 或 Greetings.xaml.cs，然后选择以下行： `MessageBox.Show("Hello.")`  
  
2.  通过选择 **“调试”**-&gt; **“切换断点”**，从菜单中添加断点。  
  
     ![“调试”菜单上的“切换断点”命令](../ide/media/exploreide-togglebreakpoint.png "ExploreIDE-ToggleBreakpoint")  
  
     编辑器窗口最左侧边距中该代码行附近将显示一个红圈。  
  
3.  选择以下行： `MessageBox.Show("Goodbye.")`。  
  
4.  按“F9”键添加断点，然后按“F5”启动调试。  
  
5.  在 **“Greetings”** 窗口中，选择 **“Hello”** 单选按钮，然后选择 **“显示”** 按钮。  
  
     行 `MessageBox.Show("Hello.")` 将用黄色突出显示。 在 IDE 底部，“自动”、“本地”和“监视”窗口一起停靠在左侧，而“调用堆栈”、“断点”、“命令”、“即时”和“输出”窗口一起停靠在右侧。  
  
6.  在菜单栏上，选择 **“调试”**-> **“跳出”**。  
  
     应用程序继续执行，并将显示出带有“Hello”的消息框。  
  
7.  选择消息框上的 **“确定”** 按钮将其关闭。  
  
8.  在 **“Greetings”** 窗口中，选择 **“Goodbye”** 单选按钮，然后选择 **“显示”** 按钮。  
  
     行 `MessageBox.Show("Goodbye.")` 将用黄色突出显示。  
  
9. 按“F5”键继续调试。 当消息框出现时，选择消息框上的 **“确定”** 按钮将其关闭。  
  
10. 关闭应用程序窗口，停止调试。  
  
11. 在菜单栏上，选择 **“调试”**-> **“禁用所有断点”**。  
  
### <a name="build-a-release-version-of-the-application"></a>生成应用程序的发布版本  
 确认一切就绪后，可以准备该应用程序的发布版本。  
  
#### <a name="to-clean-the-solution-files-and-build-a-release-version"></a>要清理解决方案文件并生成发布版本  
  
1.  在主菜单中，依次选择“生成”、“清理解决方案”，删除上一生成过程中创建的中间文件和输出文件。 这不是必需的，但它会清理调试生成输出。  
  
     ![“生成”菜单上的“清理解决方案”命令](../ide/media/exploreide-cleansolution.png "ExploreIDE-CleanSolution")  
  
2.  使用工具栏（当前显示“调试”）上的下拉列表控件把 HelloWPFApp 的生成配置从“调试”更改为“发布”。  
  
     ![选定了“发布”的“标准”工具栏](../ide/media/exploreide-releaseversion.png "ExploreIDE-ReleaseVersion")  
  
3.  选择“生成”，然后选择“生成解决方案”来生成解决方案。  
  
     ![“生成”菜单上的“生成解决方案”命令](../ide/media/exploreide-buildsolution.png "ExploreIDE-BuildSolution")  
  
祝贺你完成本演练！ 可在解决方案和项目目录 (...\HelloWPFApp\HelloWPFApp\bin\Release\\) 下找到生成的 .exe 文件。 如要了解更多示例，请参阅 [Visual Studio Samples](../ide/visual-studio-samples.md)。  
  
## <a name="see-also"></a>请参阅
[Visual Studio 2017 中的新增功能](../ide/whats-new-in-visual-studio.md)   
[Visual Studio 开发入门](../ide/get-started-developing-with-visual-studio.md)   
[工作效率提示](../ide/productivity-tips-for-visual-studio.md)