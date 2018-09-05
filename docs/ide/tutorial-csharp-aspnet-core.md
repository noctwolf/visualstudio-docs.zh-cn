---
title: Visual Studio 中的 C# 和 ASP.NET Core 入门
description: 了解如何在 Visual Studio 中使用 C# 逐步创建 ASP.NET Core Web 应用。
ms.custom: ''
ms.date: 08/10/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: fb1532a76d9bc530146ba5a0f563bcaa9389226c
ms.sourcegitcommit: db94ca7a621879f98d4c6aeefd5e27da1091a742
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2018
ms.locfileid: "42626998"
---
# <a name="tutorial-get-started-with-c-and-aspnet-core-in-visual-studio"></a>教程：Visual Studio 中的 C# 和 ASP.NET Core 入门

本教程介绍了在 Visual Studio 中使用 ASP.NET Core 进行 C# 开发的相关内容。在本教程中，你将创建一个 C# ASP.NET Core Web 应用、对其进行更改、浏览 IDE 的部分功能并运行应用。

如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)页免费安装。

## <a name="create-a-project"></a>创建项目

首先，创建一个 ASP.NET Core 项目。 项目类型随附了网站所需的全部模板文件，无需添加任何内容！

1. 打开 Visual Studio 2017。

2. 在顶部菜单栏，依次选择“文件” > “新建” > “项目”。 

3. 在“新建项目”对话框左侧的窗格中，展开“Visual C#”和“Web”，然后选择“.NET Core”。 在中间窗格中，选择“ASP.NET Core Web 应用程序”。 然后，将文件命名为 MyCoreApp 并选择“确定”。

   ![Visual Studio IDE 中“新建项目”对话框中的 ASP.NET Core Web 应用程序项目模板](../ide/media/csharp-aspnet-choose-template-name-mycoreapp-mvc.png)

### <a name="add-a-workload-optional"></a>添加工作负载（可选）

如果未显示“ASP.NET Core Web 应用程序”项目模板，可通过添加“ASP.NET 和 Web 开发”工作负载获取它。 可通过以下两种方式添加此工作负载，具体取决于计算机上安装的 Visual Studio 2017 更新。

#### <a name="option-1-use-the-new-project-dialog-box"></a>方式 1：打开“新建项目”对话框

1. 选择“新建项目”对话框左窗格中的“打开 Visual Studio 安装程序”链接。

   ![选择“新建项目”对话框中的“打开 Visual Studio 安装程序”链接](../ide/media/vs-open-visual-studio-installer-generic.png)

1. Visual Studio 安装程序启动。 选择“ASP.NET 和 Web 开发”工作负载，然后选择“修改”。

   ![Visual Studio 安装程序中的 .NET Core 跨平台开发工作负荷](../ide/media/quickstart-aspnet-workload.png)

   （你可能需要关闭 Visual Studio，然后才能继续安装新的工作负载。）

#### <a name="option-2-use-the-tools-menu-bar"></a>方式 2：使用“工具”菜单栏

1. 取消“新建项目”对话框。 然后，从顶部菜单栏中选择“工具” > “获取工具和功能”。

1. Visual Studio 安装程序启动。 选择“ASP.NET 和 Web 开发”工作负载，然后选择“修改”。

   （你可能需要关闭 Visual Studio，然后才能继续安装新的工作负载。）

### <a name="add-a-project-template"></a>添加项目模板

1. 在“新建 ASP.NET Core Web 应用程序”对话框中，选择“Web 应用程序(模型-视图-控制器)”项目模板。

1. 验证顶部下拉菜单中是否显示 ASP.NET Core 2.0。 然后选择“确定”。

   ![“新建 ASP.NET Core Web 应用程序”对话框](../ide/media/new-project-csharp-aspnet-web-app-mvc.png)

### <a name="about-your-solution"></a>关于解决方案

此解决方案遵循模型-视图-控制器 (MVC) 体系结构模式，将应用分成 3 个主要组件：

* **模型**包含表示应用数据的类。 模型类使用验证逻辑来对该数据强制实施业务规则。 通常，模型对象检索模型状态并将其存储在数据库中。
* **视图**是显示应用用户界面 (UI) 的组件。 此 UI 通常会显示模型数据。
* **控制器**包含处理浏览器请求的类。 它们检索模型数据并调用返回响应的视图模板。 在 MVC 应用中，视图仅显示信息；控制器处理并响应用户输入和交互。

MVC 模式有助于创建比传统单片应用更易于测试和更新的应用。

## <a name="tour-your-solution"></a>浏览解决方案

 1. 项目模板会创建一个解决方案，其中包含一个名为 MyCoreApp 的 ASP.NET Core 项目。 展开项目节点，显示其内容。

    ![Visual Studio 中的 ASP.NET 解决方案资源管理器](../ide/media/csharp-aspnet-solution-explorer-mycoreapp-mvc.png)

 1. 从“控制器”文件夹打开 HomeController.cs 文件。

     ![Visual Studio 解决方案资源管理器中的 HomeController.cs 文件](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

 1. 查看 HomeController.cs 文件。

     ![Visual Studio 代码窗口中的 HomeController.cs](../ide/media/csharp-aspnet-home-controller-code.png)

 1. 项目还有一个“视图”文件夹，其中包含映射到每个控制器的子文件夹。 例如，/Home/About 路径的视图 CSHTML 文件（HTML 的扩展）将位于 *Views/Home/About.cshtml*。 打开该文件。

     ![Visual Studio 解决方案资源管理器中的 About.cshtml 文件](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

    此 CSHTML 文件使用 Razor 语法，基于标准标记和内联 C# 的组合来呈现 HTML。

     ![Visual Studio 代码窗口中的 About.cshtml](../ide/media/csharp-aspnet-about-cshtml-code.png)

    >[!NOTE]
    > 要了解有关 Razor 的更多信息，请参阅[通过 Razor 语法实现 C# 和 ASP.NET 入门](/aspnet/web-pages/overview/getting-started/introducing-razor-syntax-c) 页。

 1. 该项目还包含一个 wwwroot 文件夹，它是网站的根。 展开文件夹以查看其内容。

     ![Visual Studio 解决方案资源管理器中的 wwwroot 文件夹](../ide/media/csharp-aspnet-solution-wwwroot.png)

    可将静态站点内容&mdash;如 CSS、图像和 JavaScript 库&mdash;直接放在所需的路径中。

 1. 有几个配置文件可在运行时管理项目、包和应用。 例如，默认应用程序[配置](/aspnet/core/fundamentals/configuration)存储在 appsettings.json 中。 但是，可使用 appsettings.Development.json 替代这些设置。 展开 appsettings.json 文件以查看 appsettings.Development.json 文件。

     ![Visual Studio 解决方案资源管理器中的配置文件](../ide/media/csharp-aspnet-solution-explorer-config-files.png)

## <a name="run-debug-and-make-changes"></a>运行、调试和更改

1. 在 IDE 中选择“IIS Express”按钮，在调试模式下生成并运行应用。 （或者，按 F5 或从菜单栏选择“调试”>“启动调试”。）

     ![在 Visual Studio 中选择“IIS Express”按钮](../ide/media/csharp-aspnet-iis-express-button.png)

     > [!NOTE]
     > 如果看到内容为“无法连接到 Web 服务器‘IIS Express’”的错误消息，请关闭 Visual Studio，再使用右键单击菜单或上下文菜单中的“以管理员身份运行”选项打开它。 然后，再次运行应用。

1. Visual Studio 启动浏览器窗口。 选择“关于”。

   ![在应用的浏览器窗口中选择“关于”](../ide/media/csharp-aspnet-browser-page.png)

   此外，浏览器中的“关于”页呈现 HomeController.cs 文件中设置的文本。

   ![查看“关于”页面上的文本](../ide/media/csharp-aspnet-browser-page-about.png)

1. 保持浏览器窗口呈打开状态并返回 Visual Studio。 打开 Controllers/HomeController.cs（如果尚未打开）。

   ![从 Visual Studio 解决方案资源管理器中打开 HomeController.cs 文件](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

1. 在 About 方法的第一行设置一个断点。 为此，请单击边距或将光标置于该行上并按 F9。

   此行在 Views/Home/About.cshtml处 CSHTML 页面中呈现的 ViewData 集合中设置一些数据。

   ![在 About.cshtml 中 About 方法的第一行设置一个断点。  ](../ide/media/csharp-aspnet-home-controller-code-set-breakpoint.png)

1. 返回到浏览器，并刷新“关于”页。 这会触发 Visual Studio 中的断点。

1. 在 Visual Studio 中，将鼠标悬停在 ViewData成员上以查看其数据。

   ![查看 About 方法的 ViewData 的成员，了解详细信息](../ide/media/csharp-aspnet-home-controller-view-breakpoint-info.png)

1. 使用用以添加断点的相同方式删除应用程序断点。

1. 打开 Views/Home/About.cshtml。

   ![在解决方案资源管理器中选择 About.cshtml](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

1. 将文本“additional”更改为“changed”并保存文件。

   ![将文本“additional”更改为“changed”](../ide/media/csharp-aspnet-about-cshtml-code-change.png)

1. 返回浏览器窗口，查看更新的文本。 （如果看不到更改的文本，请刷新浏览器。）

    ![刷新浏览器窗口以查看更改的文本](../ide/media/csharp-aspnet-browser-page-about-changed.png)

1. 从工具栏选择“停止调试”按钮来停止调试。 （或者，按 Shift+F5 或从菜单栏选择“调试” > “停止调试”。）

   ![在工具栏上，选择“停止调试”按钮](../ide/media/csharp-aspnet-stop-debugging.png)

## <a name="quick-answers-faq"></a>快速解答常见问题

下面是一个快速 FAQ，突出介绍了一些关键概念。

### <a name="what-is-c"></a>什么是 C#？

[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework) 是一种类型安全且面向对象的编程语言，其可靠且易于学习。

### <a name="what-is-aspnet-core"></a>什么是 ASP.NET Core？

ASP.NET Core 是开放源跨平台框架，用于生成基于 Internet 连接的应用程序，例如 Web 应用和服务。 ASP.NET Core 应用可以在 .NET Core 或 .NET Framework 上运行。 可以在 Windows、Mac 和 Linux 上跨平台开发和运行 ASP.NET Core 应用。 ASP.NET Core 在 [GitHub](https://github.com/aspnet/home) 为开放源。

### <a name="what-is-visual-studio"></a>什么是 Visual Studio？

Visual Studio 是适用于开发人员的生产力工具集成开发套件。 可将其视为可用于创建程序和应用程序的程序。

## <a name="next-steps"></a>后续步骤

恭喜你完成本教程！ 希望你已对 C#、ASP.NET Core 和 Visual Studio IDE 有了一定了解。 要详细了解如何使用 C# 和 ASP.NET 创建 Web 应用或网站，请继续学习以下教程：

> [!div class="nextstepaction"]
> [使用 ASP.NET Core 创建 MVC Web 应用](/aspnet/core/tutorials/first-mvc-app/start-mvc?view=aspnetcore-2.1&tabs=aspnetcore2x)
>
> [!div class="nextstepaction"]
> [使用 ASP.NET Core 创建 Razor 页面 Web 应用](/aspnet/core/tutorials/razor-pages/?view=aspnetcore-2.1)

## <a name="see-also"></a>请参阅

[使用 Visual Studio 将 Web 应用发布到 Azure App Service](..//deployment/quickstart-deploy-to-azure.md)