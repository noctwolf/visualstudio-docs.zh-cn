---
title: 使用 Visual Basic 创建首个控制台应用
description: 了解如何在 Visual Studio 中使用 Visual Basic 逐步创建简单的 Hello World 控制台应用。
ms.date: 12/10/2017
ms.prod: visual-studio-dev15
ms.custom: seodec18
ms.topic: quickstart
ms.devlang: vb
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- vb
ms.workload:
- multiple
ms.openlocfilehash: 7ddb96187f270e1a7158d007302ec16b1bb7ad22
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55034799"
---
# <a name="quickstart-create-your-first-console-app-in-visual-studio-with-visual-basic"></a>快速入门：使用 Visual Basic 在 Visual Studio 中创建第一个控制台应用

在这个 5-10 分钟的 Visual Studio 集成开发环境 (IDE) 简介中，你将了解如何创建在控制台上运行的简单 Visual Basic 应用程序。

如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)页免费安装。

## <a name="create-a-project"></a>创建项目

首先，先创建一个 Visual Basic 应用程序项目。 项目类型随附了所需的全部模板文件，无需添加任何内容！

1. 打开 Visual Studio 2017。

2. 在顶部菜单栏，依次选择“文件” > “新建” > “项目”。

3. 在“新建项目”对话框左侧的窗格中，展开“Visual Basic”，然后选择“.NET Core”。 在中间窗格中，选择“控制台应用(.NET Core)”。 随后将项目命名为 HelloWorld。

   ![Visual Studio IDE 中“新建项目”对话框中的控制台应用 (.NET Core) 项目模板](../ide/media/new-project-vb-dotnetcore-helloworld-console-app.png)

     如果没有看到“控制台应用(.NET Core)”项目模板，请单击“新建项目”对话框左侧窗格中的“打开 Visual Studio 安装程序”链接。

   ![单击“新建项目”对话框中的“打开 Visual Studio 安装程序”链接](../ide/media/vb-open-visual-studio-installer-hello-world.png)

     Visual Studio 安装程序启动。 选择“.NET Core 跨平台开发”工作负载，然后选择“修改”。

     ![Visual Studio 安装程序中的 .NET Core 跨平台开发工作负载](../ide/media/dot-net-core-xplat-dev-workload.png)

## <a name="create-the-application"></a>创建应用程序

选择 Visual Basic 项目模板并为项目命名后，Visual Studio 会创建一个简单的“Hello World”应用程序。 它通过调用 <xref:System.Console.WriteLine%2A> 方法在控制台窗口中 显示文本字符串“Hello World!”。

![查看模板中的默认 Hello World 代码](../ide/media/vb-console-helloworld-template.png)

在 IDE 中单击“HelloWorld”按钮，即可在“调试”模式下运行程序。

  ![单击“Hello World”按钮，在“调试”模式下运行程序](../ide/media/vb-console-hello-world-button.png)

进行此操作时，控制台窗口短暂出现后就会关闭。 这是因为 `Main` 方法在执行其单个语句后就会终止，应用程序因而结束。

### <a name="add-some-code"></a>添加一些代码

先添加一些代码来暂停应用程序，然后请求用户输入。

1. 在 <xref:System.Console.WriteLine%2A> 方法调用后面紧接着添加以下代码：

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```

    此时程序暂停，直到按下某个键。

2. 在菜单栏中，选择“生成” > “生成解决方案”。

   这会将程序编译成一种中间语言 (IL)，然后由实时 (JIT) 编译器转换成二进制代码。

## <a name="run-the-application"></a>运行此应用程序

1. 单击工具栏上的“HelloWorld”按钮。

   ![单击“Hello World”按钮，从工具栏运行程序](../ide/media/vb-console-hello-world-button.png)

2. 按任意键关闭控制台窗口。

   ![显示 Hello World 和 Press any key to continue 的控制台窗口](../ide/media/vb-console-hello-world-press-any-key.png)

## <a name="next-steps"></a>后续步骤

祝贺你完成此快速入门！ 希望你已对 Visual Basic 和 Visual Studio IDE 有了一定了解。 若要更加深入地了解，请继续学习下面的教程。

> [!div class="nextstepaction"]
> [Visual Studio 中的 Visual Basic 入门](../get-started/visual-basic/tutorial-console.md)
