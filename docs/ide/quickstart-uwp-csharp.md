---
title: 快速入门：在 Visual Studio 中使用 XAML 和 C# 创建第一个通用 Windows 平台应用程序 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2018
ms.prod: visual-studio-dev15
ms.technology:
- vs-acquisition
ms.topic: quickstart
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: dd638a539b8956716aa60b5361bd003c18d35f9b
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "36283320"
---
# <a name="quickstart-create-your-first-universal-windows-platform-application-in-visual-studio-with-xaml-and-c35"></a>快速入门：在 Visual Studio 中使用 XAML 和 C&#35 创建第一个通用 Windows 平台应用程序

在这个 5-10 分钟的 Visual Studio 集成开发环境 (IDE) 简介中，你将创建能在任何 Windows 10 设备上运行的"Hello World"应用。 为此，将使用通用 Windows 平台 (UWP) 项目模板、Extensible Application Markup Language (XAML) 和 C# 编程语言。

如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)页免费安装。

## <a name="create-a-project"></a>创建项目

首先，创建通用 Windows 平台项目。 项目类型随附了所需的全部模板文件，无需添加任何内容！

1. 打开 Visual Studio 2017。

2. 在顶部菜单栏，依次选择“文件” > “新建” > “项目”。

3. 在“新建项目”对话框的左侧窗格中，展开“Visual C#”，然后选择“Windows 通用”。 在中间窗格中，选择“空白应用(通用 Windows)”。 随后将项目命名为 HelloWorld，并选择“确定”。

   ![Visual Studio IDE 中“新建项目”对话框中的 Windows 通用项目模板](../ide/media/new-project-csharp-uwp-helloworld.png)

   > [!NOTE]
   > 如果没有看到“空白应用(通用 Windows)”项目模板，请单击“新建项目”对话框左侧窗格中的“打开 Visual Studio 安装程序”链接。<br><br>![单击“新建项目”对话框中的“打开 Visual Studio 安装程序”链接](../ide/media/vb-open-visual-studio-installer-hello-world.png)<br><br>Visual Studio 安装程序启动。 选择“通用 Windows 平台开发”工作负载，然后选择“修改”。<br><br>![Visual Studio 安装程序中的通用 Windows 平台开发工作负载](../ide/media/uwp-dev-workload.png)

4. 出现“新式通用 Windows 平台项目”对话框时，选择“确定”。

   ![接受“新式通用 Windows 平台项目”对话框中的默认目标版本和最小版本设置](../ide/media/new-uwp-project-target-minver-dialog.png)

  > [!NOTE]
  > 如果你是第一次使用 Visual Studio 创建 UWP 应用，则可能会出现“设置”对话框。 选择“开发人员模式”，然后选择“是”。<br><br>
 ![在“UWP 设置”对话框中启用开发人员模式](../ide/media/enable-developer-mode.png)<br><br>Visual Studio 会为你安装其他开发人员模式包。 包安装完成时，请关闭“设置”对话框。

## <a name="create-the-application"></a>创建应用程序

现在开始开发吧。 你可以添加按钮控件，向按钮添加操作，然后启用"Hello World"应用查看效果。

### <a name="add-a-button-to-the-design-canvas"></a>向设计画布添加按钮

1. 在解决方案资源管理器中双击“MainPage.xaml”，打开拆分视图。

  ![在解决方案资源管理器中，打开 MainPage.xaml ](../ide/media/uwp-solution-explorer-MainPage-xaml.png)

  出现两个窗格：一个是“XAML 设计器”，其中包含设计画布；另一个是“XAML 编辑器”，可用于添加或更改代码。

  ![XAML 编辑器中的“XAML 设计器”窗格](../ide/media/uwp-xaml-editor.png)

2. 选择“工具箱”，打开“工具箱”弹出窗口。

  ![单击“工具箱”，打开“工具箱”弹出窗口](../ide/media/uwp-toolbox.png)

  （如果看不到“工具箱”选项，可从菜单栏打开。 为此，请选择“视图” > “工具箱”。 或按 Ctrl+Alt+X。）

3. 单击“固定”图标，固定“工具箱”窗口。

  ![单击“固定”图标，固定“工具箱”窗口](../ide/media/uwp-toolbox-autohide.png)

4. 单击“按钮”控件，然后将其拖到设计画布上。

   ![单击“按钮”控件并将其拖到设计画布上](../ide/media/uwp-toolbox-add-button-control.png)

  如果在 XAML 编辑器中查看代码，就会看到该按钮也已添加到此处：

  ![单击“按钮”控件并将其拖到设计画布上](../ide/media/uwp-xaml-control-code-window.png)

### <a name="add-a-label-to-the-button"></a>向按钮添加标签

1. 在 XAML 编辑器中，将按钮内容的值从“按钮”更改为"Hello World!"

   ![将按钮内容的值更改为 Hello World](../ide/media/uwp-change-button-text-in-xaml-code-window.png)

2. 请注意 XAML 设计器中的按钮也会随之更改。

   ![设计画布上的按钮更改为 Hello World](../ide/media/uwp-button-text-change-in-design-canvas.png)

### <a name="add-an-event-handler"></a>添加事件处理程序

“事件处理程序”听起来复杂，但只不过是事件发生时，被调用代码的另一种名称。 在本例中，事件处理程序会将操作添加到"Hello World!" 按钮。

1. 双击设计画布上的按钮控件。

2. 在 MainPage.xaml.cs（代码隐藏页）中编辑事件处理程序代码。

 现在，有趣的事情发生了。 默认事件处理程序如下所示：

   ![默认 Button_Click 事件处理程序 ](../ide/media/uwp-button-click-code.png)

 在我们更改后，该事件处理程序如下所示：

    ![新的异步 Button_Click 事件处理程序 ](../ide/media/uwp-add-hello-world-async-code.png)

  以下是可用于复制和粘贴的代码：

  ```C#
  private async void Button_Click(object sender, RoutedEventArgs e)
         {
             MediaElement mediaElement = new MediaElement();
             var synth = new Windows.Media.SpeechSynthesis.SpeechSynthesizer();
             Windows.Media.SpeechSynthesis.SpeechSynthesisStream stream = await synth.SynthesizeTextToStreamAsync("Hello, World!");
             mediaElement.SetSource(stream, stream.ContentType);
             mediaElement.Play();
         }
  ```

#### <a name="what-did-we-just-do"></a>我们刚才做了什么？

代码使用某些 Windows API 创建语音合成对象，然后向此对象通过一些文本用于朗读。 （有关使用 `SpeechSynthesis` 的详细信息，请参阅 <xref:System.Speech.Synthesis>。）

## <a name="run-the-application"></a>运行此应用程序

该生成、部署和启动“Hello World”UWP 应用了，以了解它的视听效果。 操作方法如下。

1. 选择“本地计算机”以启动该应用程序。

   ![单击“本地计算机”以启动并调试 UWP 应用](../ide/media/uwp-start-or-debug.png)

   （或者，也可以在菜单栏选择“调试” > “开始调试”或按 F5 启动应用。）

2. 应用在初始屏幕消失后不久出现，请查看该应用。 此应用应类似于以下所示：

   ![UWP“Hello World”应用](../ide/media/uwp-hello-world-app.png)

3. 单击“Hello world”按钮。

 Windows 10 设备将直接说“Hello, World!”

4. 要关闭应用，请在工具栏中单击“停止调试”按钮 （或者，从菜单栏选择“调试” > “停止调试”或按 Shift+F5。）

## <a name="next-steps"></a>后续步骤

祝贺你完成此快速入门！ 我们希望你能了解一些与 UWP 和 Visual Studio IDE 有关的基础知识。 要更加深入地了解，请继续学习下面的教程：

> [!div class="nextstepaction"]
> [创建用户界面](/windows/uwp/design/basics/xaml-basics-ui)
