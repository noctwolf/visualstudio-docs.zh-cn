---
title: 使用 C# 创建 ASP.NET Core Web 应用
description: 了解如何在 Visual Studio 中使用 C# 和 ASP.NET Core 逐步创建简单的 Hello World Web 应用。
ms.date: 02/01/2019
ms.custom: mvc,seodec18
ms.topic: quickstart
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 60f7c7bd7d0a3073f75d4ece7012601ded8eb059
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55957788"
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>快速入门：使用 Visual Studio 创建首个 ASP.NET Core Web 应用

在这篇关于如何使用 Visual Studio 的 5-10 分钟简介中，将使用 ASP.NET 项目模板和 C# 编程语言创建一个简单的“Hello World”Web 应用。

## <a name="before-you-begin"></a>在开始之前

### <a name="install-visual-studio"></a>安装 Visual Studio

如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)页免费安装。

### <a name="choose-your-theme-optional"></a>选择主题（可选）

本快速入门教程包含使用深色主题的屏幕截图。 如果没有深色主题但想要使用，请参阅[个性化设置 Visual Studio IDE 和编辑器](quickstart-personalize-the-ide.md)页面，了解具体方法。

## <a name="create-a-project"></a>创建项目

首先，将创建 ASP.NET Core web 应用程序项目。 项目类型随附了用于创建 Web 应用的全部模板文件，无需添加任何内容！

1. 打开 Visual Studio 2017。

1. 在顶部菜单栏，依次选择“文件” > “新建” > “项目”。

1. 在“新建项目”对话框的左侧窗格中，展开“Visual C#”，然后选择“.NET Core”。 在中间窗格中，选择“ASP.NET Core Web 应用程序”。 <br/><br/>然后，将文件命名为 `HelloWorld`，并选择“确定”。

   ![创建面向 C# 的新 ASP.NET Core Web 应用程序项目](../ide/media/csharp-aspnet-choose-template-name-file.png)

   > [!NOTE]
   > 如果没有看到“.NET Core”项目模板类别，请选择左侧窗格中的“打开 Visual Studio 安装程序”链接。 （根据你的显示设置，进行滚动以便查看。）
   >
   > ![从“新建项目”对话框中打开 Visual Studio 安装程序](../ide/media/open-visual-studio-installer.png)
   >
   > Visual Studio 安装程序启动。 选择“ASP.NET 和 Web 开发”工作负载，然后选择“修改”。
   >
   > ![VS 安装程序的 ASP.NET 工作负载](../ide/media/quickstart-aspnet-workload.png)
   >
   > （你可能需要关闭 Visual Studio，然后才能继续安装新的工作负载。）

1. 在“新建 ASP.NET Core Web 应用程序”对话框中，从顶部下拉菜单选择“ASP.NET Core 2.1”。 接下来，选择“Web 应用程序”，然后选择“确定”。

   ![“新建 ASP.NET Core Web 应用程序”对话框](../ide/media/aspnet-core-2dot1.png)

   > [!NOTE]
   > 如果没有看到“ASP.NET Core 2.1”或更高版本，请确保你运行的是最新版本的 Visual Studio。 有关如何更新安装的详细信息，请参阅[将 Visual Studio 2017 更新到最新版本](../install/update-visual-studio.md)页面。

不久之后，Visual Studio 将打开你的项目文件。

## <a name="create-and-run-the-app"></a>创建并运行应用

1. 在“解决方案资源管理器”中，展开“Pages”文件夹，然后选择“About.cshtml”。

   ![从“解决方案资源管理器”中选择 About.cshtml 文件](../ide/media/csharp-aspnet-about-page-html-file.png)

   此文件对应于 Web 应用中名为“关于”的页，该页在 Web 浏览器中运行。

   ![Web 应用中的“About”页](../ide/media/csharp-aspnet-about-page.png)

   在编辑器中，你将看到“About”页的“其他信息”区域的 HTML 代码。

   ![Visual Studio 编辑器中“其他信息”区域的 HTML 代码](../ide/media/csharp-aspnet-about-cshtml-page.png)

1. 将“其他信息”文本更改为“Hello World!”。

   ![更改 Visual Studio 编辑器中“其他信息”区域的默认 HTML 代码](../ide/media/csharp-aspnet-about-cshtml-page-hello-world.png)

1. 在“解决方案资源管理器”中，展开“About.cshtml”，然后选择“About.cshtml.cs”。 （此文件也对应于 web 浏览器中的“关于”页。）

   ![从“解决方案资源管理器”中选择 About.cshtml 文件](../ide/media/csharp-aspnet-about-page-code-file.png)

   在编辑器中，你将看到包含“关于”页的“应用程序说明”区域的文本的 C# 代码。

   ![Visual Studio 编辑器中“应用程序说明”区域的 C# 代码](../ide/media/csharp-aspnet-about-cshtml-cs-code.png)

1. 将“应用程序说明”消息文本更改为“我的消息是什么？”。

   ![更改 Visual Studio 编辑器中“应用程序说明”区域的默认消息文本](../ide/media/csharp-aspnet-about-cshtml-cs-message.png)

1. 选择“IIS Express”或按 Ctrl+F5 运行此应用，并在 Web 浏览器中打开它。

   ![在 Visual Studio 中选择“IIS Express”按钮](../ide/media/csharp-aspnet-helloworld-iisbutton.png)

   > [!NOTE]
   > 如果收到错误消息“无法连接到 Web 服务器 "IIS Express"”，或者收到提及 SSL 证书的错误消息，请关闭 Visual Studio。 接下来，右键单击上下文菜单，使用其中的“以管理员身份运行”选项打开 Visual Studio。 然后，再次运行应用。

1. 在 Web 浏览器中，验证“关于”页是否包含更新的文本。

   ![查看更新的“关于”页，其中包含你所做的更改](../ide/media/csharp-aspnet-about-page-hello-world.png)

1. 关闭 Web 浏览器。

### <a name="review-your-work"></a>检查工作

查看以下动画以检查你在上一节中完成的工作。

  ![查看动画 .gif 文件，该文件显示如何在 Visual Studio 中创建和运行简单的 C# ASP.NET Core Web 应用](../ide/media/csharp-aspnet-animated-hello-world.gif)

祝贺你完成此快速入门！ 希望你已对 C#、ASP.NET Core 和 Visual Studio IDE 有了一定了解（集成的开发环境）。

## <a name="next-steps"></a>后续步骤

要更加深入地了解，请继续学习下面的教程：

> [!div class="nextstepaction"]
> [Visual Studio 中的 C# 和 ASP.NET 入门](../get-started/csharp/tutorial-aspnet-core.md)

## <a name="see-also"></a>请参阅

[使用 Visual Studio 将 Web 应用发布到 Azure App Service](../deployment/quickstart-deploy-to-azure.md)
