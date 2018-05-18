---
title: 在 Visual Studio 中使用 C# 创建 ASP.NET Core web 应用
description: 了解如何在 Visual Studio 中使用 C# 逐步创建 ASP.NET Core Web 应用。
ms.custom: mvc
ms.date: 10/10/2017
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: quickstart
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 1b74f47201c706cbb4fe4a4f0eca647b350d9a72
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2018
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>快速入门：使用 Visual Studio 创建首个 ASP.NET Core Web 应用

在这个对 Visual Studio 集成开发环境 (IDE) 的 5-10 分钟简介中，可以创建简单的 C# ASP.NET Core web 应用程序。

如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)页免费安装。

## <a name="create-a-project"></a>创建项目

首先，创建一个 ASP.NET Core web 应用程序项目。 即使尚未添加任何内容，项目类型随附的模板文件里也包含一个功能性 web 应用程序！

1. 打开 Visual Studio 2017。

1. 在顶部菜单栏，依次选择“文件” > “新建” > “项目”。

1. 在“新建项目”对话框的左窗格中，展开“Visual C#”，然后选择“.NET Core”。 在中间窗格中，选择“ASP.NET Core Web 应用程序”，然后选择“确定”。

     如果没有看到“.NET Core”项目模板类别，请选择左侧窗格中的“打开 Visual Studio 安装程序”链接。 Visual Studio 安装程序启动。 选择“ASP.NET 和 web 开发”工作负载，然后选择“修改”。

     ![VS 安装程序的 ASP.NET 工作负载](../ide/media/quickstart-aspnet-workload.png)

1. 在“新建 ASP.NET Core Web 应用程序”对话框中，从顶部下拉菜单选择“ASP.NET Core 2.0”。 （如果没有在列表中看到“ASP.NET Core 2.0”，请通过“下载”链接进行安装，该链接显示在对话框顶部附近的黄色栏中。）选择 **“确定”**。

   ![“新建 ASP.NET Core Web 应用程序”对话框](../ide/media/quickstart-aspnet-core20.png)

## <a name="explore-the-ide"></a>探索 IDE

1. 在“解决方案资源管理器”工具栏，展开“Pages”文件夹，然后选择“About.cshtml”，在编辑器中将它打开。 该文件对应于 web 应用程序中名为“About”的页。

1. 在编辑器中，选择 `AboutModel`然后按“F12”或选择上下文菜单（右键单击）中的“转到定义”。 此命令将转到 `AboutModel` C# 类的定义。

   ![转到定义上下文菜单](../ide/media/quickstart-aspnet-gotodefinition.png)

1. 接下来将使用简单快捷方式清理文件顶部的 `using` 指令。 选择任何灰色的 using 指令，插入点下方或左边距会显示[快速操作](../ide/quick-actions.md)灯泡。 选择此灯泡，然后选择“删除不必要的 Using”。

     从文件中删除不必要的 using。

1. 在 `OnGet()` 方法中，将主体更改为以下代码：

 ```csharp
 public void OnGet()
 {
     string directory = Environment.CurrentDirectory;
     Message = String.Format("Your directory is {0}.", directory);
 }
 ```

1. “环境”和“字符串”下方将会出现两条波浪形下划线，因为这两种类型不在范围内。 打开“错误列表”工具栏，查看此处列出的相同错误。 （如果没有看到“错误列表”工具栏，请选择顶部菜单栏中的“视图” > “错误列表”。）

   ![错误列表](../ide/media/quickstart-aspnet-errorlist.png)

1. 在编辑器窗口中，将光标放在包含错误的任意一条线上，然后选择左边距中的“快速操作”灯泡。 从下拉菜单中，选择“使用系统”将此指令添加到文件顶部并解析错误。

## <a name="run-the-application"></a>运行此应用程序

1. 按 Ctrl+F5 运行此应用程序，并在 Web 浏览器中打开它。

1. 在网站顶部，选择“About”可查看添加在“About”页的 `OnGet()` 方法中的目录消息。

1. 关闭 Web 浏览器。

> [!NOTE]
> 如果看到内容为“无法连接到 Web 服务器 'IIS Express'”的错误消息，请关闭 Visual Studio，再使用右键单击或关联菜单中的“以管理员身份运行”选项打开它。 然后，再次运行应用。

祝贺你完成此快速入门！ 我们希望你已对 Visual Studio IDE 有了一定了解。 若要深入了解其功能，请继续阅读目录中“教程”部分的教程。

## <a name="next-steps"></a>后续步骤
祝贺你完成此快速入门！ 希望你已对 C#、ASP.NET Core 和 Visual Studio IDE 有了一定了解。 若要更加深入地了解，请继续学习下面的教程。

> [!div class="nextstepaction"]
> [Visual Studio 中的 C# 和 ASP.NET 入门](tutorial-csharp-aspnet-core.md)
