---
title: 在 Visual Studio 中使用 Visual Basic 创建 Windows 窗体应用 | Microsoft Docs
description: 了解如何在 Visual Studio 中使用 Visual Basic 分步创建 Windows 窗体应用。
ms.custom: ''
ms.date: 12/04/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: article
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: ghogen
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: d3a6593a6e459b16541358a0e89dc5bc21fde982
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-windows-forms-app-in-visual-studio-with-visual-basic"></a>在 Visual Studio 中使用 Visual Basic 创建 Windows 窗体应用
在此 Visual Studio 集成开发环境 (IDE) 简介中，了解如何创建具有基于 Windows 的用户界面 (UI) 的简单 Visual Basic 应用程序。

如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)页免费安装。

## <a name="create-a-project"></a>创建项目
首先，先创建一个 Visual Basic 应用程序项目。 项目类型随附了所需的全部模板文件，无需添加任何内容。  

1. 打开 Visual Studio 2017。  

2. 在顶部菜单栏，依次选择“文件” > “新建” > “项目...”。  

3. 在“新建项目”对话框左侧的窗格中，展开“Visual Basic”，然后选择“Windows 经典桌面”。 在中间窗格中，选择“Windows 窗体应用(.NET Framework)”。 随后将文件命名为 `HelloWorld`。  

     如果没有看到“Windows 窗体应用(.NET Framework)”项目模板，则取消“新建项目”对话框，然后在顶部菜单栏中依次选择“工具” > “获取工具和功能...”。Visual Studio 安装程序启动。 选择“.NET 桌面开发”工作负载，然后选择“修改”。  

     ![Visual Studio 安装程序中的 .NET Core 开发工作负载](../ide/media/install-dot-net-desktop-env.png)  

## <a name="create-the-application"></a>创建应用程序
选择 Visual Basic 项目模板并为文件命名后，Visual Studio 会打开一个窗体。 窗体就是 Windows 用户界面。 通过向窗体添加控件创建“Hello World”应用程序，然后运行该应用程序。   

### <a name="add-a-button-to-the-form"></a>向窗体添加按钮  

1. 单击“工具箱”，打开“工具箱”弹出窗口。

     ![单击“工具箱”，打开“工具箱”窗口](../ide/media/vb-toolbox-toolwindow.png)  

     （如果看不到“工具箱”弹出选项，可从菜单栏打开。 若要执行此操作，请单击“视图” > “工具箱”。 或按 Ctrl+Alt+X。）

2. 单击“固定”图标，固定“工具箱”窗口。

     ![单击“固定”图标，将“工具箱”窗口固定到 IDE](../ide/media/vb-pin-the-toolbox-window.png)  
3. 单击“按钮”控件，然后将其拖到窗体上。

     ![向窗体添加按钮](../ide/media/vb-add-a-button-to-form1.png)

4. 在“属性”窗口的“外观”部分，键入 `Click this`，然后按 Enter。

     ![向窗体上的按钮添加文本](../ide/media/vb-button-control-text.png)  

     （如果看不到“属性”窗口，可从菜单栏打开。 若要执行此操作，请单击“视图” > “属性窗口”。 或按 F4。）

5. 在“属性”窗口的“设计”部分，将名称从“Button1”更改为 `btnClickThis`，然后按 Enter。

     ![向窗体上的按钮添加功能](../ide/media/vb-button-control-function.png)

### <a name="add-a-label-to-the-form"></a>向窗体添加标签
添加创建操作的按钮控件后，我们来添加发送文本的标签控件。

1. 从“工具箱”窗口选择“标签”控件，然后将其拖到窗体上，并放到“单击此处”按钮下方。

2. 在“属性”窗口的“设计”部分，将名称从“Label1”更改为 `lblHelloWorld`，然后按 Enter。

### <a name="add-code-to-the-form"></a>向窗体添加代码

1. 在“Form1.vb [设计]”窗口中，双击“单击此处”按钮，打开“Form1.vb”窗口。

      （或者，可在“解决方案资源管理器”窗口中展开“Form1.vb”，然后单击“Form1”。）

2. 在“Form1.vb”窗口的“Private Sub”行和“End Sub”行之间，键入或粘贴 `lblHelloWorld.Text = "Hello World!"`。

     ![向窗体添加代码](../ide/media/vb-add-code-to-the-form.png)

## <a name="run-the-application"></a>运行此应用程序
1. 单击“启动”按钮运行应用程序。

     ![单击“启动”，调试和运行应用](../ide/media/vb-click-start-hello-world.png)

   将出现以下几种情况。 在 Visual Studio IDE 中，“诊断工具”窗口打开，同时还会打开一个“输出”窗口。 在 IDE 外部，会出现一个“Form1”对话框。 其中包含“单击此处”按钮和显示“Label1”的文本。

2. 单击“Form1”对话框中的“单击此处”按钮。 请注意，“Label1”文本会更改为“Hello World!”。

    ![包含 Label1 文本的“Form1”对话框 ](../ide/media/vb-form1-dialog-hello-world.png)

祝贺你完成此快速入门！ 希望你已对 Visual Basic 和 Visual Studio IDE 有了一定了解。 若要深入了解，请继续阅读目录中“教程”部分的教程。  

## <a name="see-also"></a>请参阅   
* [快速入门：使用 Visual Basic 在 Visual Studio 中创建控制台应用](quickstart-visual-basic-console.md)
* [详细了解 Visual Basic IntelliSense](visual-basic-specific-intellisense.md)  
