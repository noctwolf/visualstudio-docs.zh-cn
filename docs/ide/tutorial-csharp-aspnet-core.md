---
title: Visual Studio 中的 C# 和 ASP.NET Core 入门
ms.custom: ''
ms.date: 12/11/2017
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
ms.openlocfilehash: 3de8a60b6f9f4807bd0032fc457a9040f937c063
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34765510"
---
# <a name="get-started-with-c-and-aspnet-in-visual-studio"></a>Visual Studio 中的 C# 和 ASP.NET 入门

本教程介绍在 Visual Studio 中借助 ASP.NET Core 进行 C# 开发，将创建一个 C# ASP.NET Core Web 应用，向其添加代码，浏览 IDE 的某些功能并运行应用。

如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)页免费安装。

## <a name="before-you-begin"></a>在开始之前

下面是一个快速 FAQ，介绍一些关键概念。

### <a name="what-is-c"></a>什么是 C#？

[C#](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework) 是一种类型安全且面向对象的编程语言，其可靠且易于学习。

### <a name="what-is-aspnet-core"></a>什么是 ASP.NET Core？

ASP.NET Core 是开放源跨平台框架，用于生成基于 Internet 连接的应用程序，例如 Web 应用和服务。 ASP.NET Core 应用可以在 .NET Core 或 .NET Framework 上运行。 可以在 Windows、Mac 和 Linux 上跨平台开发和运行 ASP.NET Core 应用。 ASP.NET Core 在 [GitHub](https://github.com/aspnet/home) 为开放源。

### <a name="what-is-visual-studio"></a>什么是 Visual Studio？

Visual Studio 是适用于开发人员的生产力工具集成开发套件。 可将其视为可用于创建程序和应用程序的程序。  

## <a name="start-developing"></a>开始开发

已准备好开始开发？ 那就开始吧！

### <a name="create-a-project"></a>创建项目

首先，创建一个 ASP.NET Core 项目。 项目类型随附了所需的全部模板文件，无需添加任何内容。

1. 打开 Visual Studio 2017。

2. 在顶部菜单栏，依次选择“文件” > “新建” > “项目”。

3. 在“新建项目”对话框左侧的窗格中，展开“Visual C#”和“Web”，然后选择“.NET Core”。 在中间窗格中，选择“ASP.NET Core Web 应用程序”，将该文件命名为 MyCoreApp，然后选择“确定”。

   ![Visual Studio IDE 中“新建项目”对话框中的 ASP.NET Core Web 应用程序项目模板](../ide/media/new-project-csharp-aspnet-mycoreapp.png)

#### <a name="add-a-workload-optional"></a>添加工作负载（可选）

如果未显示“ASP.NET Core Web 应用程序”项目模板，可通过添加“ASP.NET 和 Web 开发”工作负载获取它。 可通过以下两种方式添加此工作负载，具体取决于计算机上安装的 Visual Studio 2017 更新。

##### <a name="option-1-use-the-new-project-dialog-box"></a>方式 1：打开“新建项目”对话框

1. 单击“新建项目”对话框左窗格中的“打开 Visual Studio 安装程序”链接。

   ![单击“新建项目”对话框中的“打开 Visual Studio 安装程序”链接](../ide/media/vs-open-visual-studio-installer-generic.png)

2. Visual Studio 安装程序启动。 选择“ASP.NET 和 Web 开发”工作负载，然后选择“修改”。

   ![Visual Studio 安装程序中的 .NET Core 跨平台开发工作负荷](../ide/media/asp-dot-net-web-dev-workload.png)

##### <a name="option-2-use-the-tools-menu-bar"></a>方式 2：使用“工具”菜单栏

1. 取消“新建项目”对话框，再依次选择顶部菜单栏中的“工具” > “获取工具和功能”。

2. Visual Studio 安装程序启动。 选择“ASP.NET 和 Web 开发”工作负载，然后选择“修改”。

#### <a name="add-a-project-template"></a>添加项目模板

1. 在“新建 ASP.NET Core Web 应用程序”对话框中，选择“Web 应用程序(模型-视图-控制器)”项目模板。  

2. 从顶部下拉菜单中选择“ASP.NET Core 2.0”。 （如果没有在列表中看到“ASP.NET Core 2.0”，请通过“下载”链接进行安装，该链接显示在对话框顶部附近的黄色栏中。）选择 **“确定”**。

   ![“新建 ASP.NET Core Web 应用程序”对话框](../ide/media/new-project-csharp-aspnet-web-app-mvc.png)

### <a name="about-your-solution"></a>关于解决方案

此解决方案遵循模型-视图-控制器 (MVC) 体系结构模式，将应用分成 3 个主要组件：

* **模型**包含表示应用数据的类。 模型类使用验证逻辑来对该数据强制实施业务规则。 通常，模型对象检索模型状态并将其存储在数据库中。
* **视图**是显示应用用户界面 (UI) 的组件。 此 UI 通常会显示模型数据。
* **控制器**包含处理浏览器请求的类。 它们检索模型数据并调用返回响应的视图模板。 在 MVC 应用中，视图仅显示信息；控制器处理并响应用户输入和交互。

MVC 模式有助于创建比传统单片应用更易于测试和更新的应用。

### <a name="tour-your-solution"></a>浏览解决方案

 1. 项目模板会创建一个解决方案，其中包含一个名为 MyCoreApp 的 ASP.NET Core 项目。 展开项目节点，显示其内容。

    ![Visual Studio 中的 ASP.NET 解决方案资源管理器](../ide/media/csharp-aspnet-solution-explorer-mycoreapp.png)

 2. 从“控制器”文件夹打开 HomeController.cs 文件。

     ![Visual Studio 解决方案资源管理器中的 HomeController.cs 文件](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

 3. 查看 HomeController.cs

     ![Visual Studio 代码窗口中的 HomeController.cs](../ide/media/csharp-aspnet-home-controller-code.png)

 4. 项目还有一个“视图”文件夹，其中包含映射到每个控制器的其他文件夹（以及一个“共享”视图的文件夹）。 例如，/Home/About 路径的视图 CSHTML 文件（HTML 的扩展）将位于 *Views/Home/About.cshtml*。 打开该文件。

     ![Visual Studio 解决方案资源管理器中的 About.cshtml 文件](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

 5. 此 CSHTML 文件使用 Razor 语法，基于标准标记和内联 C# 的组合来呈现 HTML。

     ![Visual Studio 代码窗口中的 About.cshtml](../ide/media/csharp-aspnet-about-cshtml-code.png)

   >[!NOTE]
   > 若要了解详细信息，请参阅[通过 Razor 语法开始使用 C# 和 ASP.NET](/aspnet/web-pages/overview/getting-started/introducing-razor-syntax-c) 页。

 6. 解决方案还包含 wwwroot文件夹，它是网站的根。 部署站点时，可以直接将静态站点内容（如 CSS、映像和 JavaScript 库）置于所需路径。

     ![Visual Studio 解决方案资源管理器中的 wwwroot 文件夹](../ide/media/csharp-aspnet-solution-wwwroot.png)

 7. 还有各种在运行时用来管理项目、包以及应用程序的配置文件。 例如，默认应用程序[配置](/aspnet/core/fundamentals/configuration)存储在 appsettings.json 中。 但可以通过为“开发”环境提供 appsettings.Development.json 文件之类的方式，基于每个环境替代部分/所有这些设置。

     ![Visual Studio 解决方案资源管理器中的配置文件](../ide/media/csharp-aspnet-solution-explorer-config-files.png)

## <a name="run-and-debug-the-application"></a>运行和调试应用程序

1. 在 IDE 中选择“IIS Express”按钮，在调试模式下生成并运行应用。 （或者，按 F5 或从菜单栏选择“调试”>“启动调试”。）

   ![在 Visual Studio 中单击“IIS Express”按钮](../ide/media/csharp-aspnet-iis-express-button.png)

  > [!NOTE]
  > 如果看到内容为“无法连接到 Web 服务器‘IIS Express’”的错误消息，请关闭 Visual Studio，再使用右键单击菜单或上下文菜单中的“以管理员身份运行”选项打开它。 然后，再次运行应用。

2. Visual Studio 启动浏览器窗口。 选择“关于”。

   ![在应用的浏览器窗口中选择“关于”](../ide/media/csharp-aspnet-browser-page.png)

 此外，浏览器中的“关于”页呈现 HomeController.cs 文件中设置的文本。

   ![查看“关于”页面上的文本](../ide/media/csharp-aspnet-browser-page-about.png)

3. 保持浏览器窗口呈打开状态并返回 Visual Studio。 打开 Controllers/HomeController.cs（如果尚未打开）。

   ![从 Visual Studio 解决方案资源管理器中打开 HomeController.cs 文件](../ide/media/csharp-aspnet-solution-explorer-home-controller.png)

4. 在 About 方法的第一行设置一个断点。 为此，请单击边距或将光标置于该行上并按 F9。

  此行在 Views/Home/About.cshtml处 CSHTML 页面中呈现的 ViewData 集合中设置一些数据。

   ![在 About.cshtml 中 About 方法的第一行设置一个断点。  ](../ide/media/csharp-aspnet-home-controller-code-set-breakpoint.png)

5. 返回到浏览器，并刷新“关于”页。 这会触发 Visual Studio 中的断点。

6. 在 Visual Studio 中，将鼠标悬停在 ViewData成员上以查看其数据。

   ![查看 About 方法的 ViewData 的成员，了解详细信息](../ide/media/csharp-aspnet-home-controller-view-breakpoint-info.png)

7. 使用用以添加断点的相同方式删除应用程序断点。

8. 打开 Views/Home/About.cshtml。

   ![在解决方案资源管理器中选择 About.cshtml](../ide/media/csharp-aspnet-solution-explorer-view-about.png)

9. 将文本“additional”更改为“changed”并保存文件。

   ![将文本“additional”更改为“changed”](../ide/media/csharp-aspnet-about-cshtml-code-change.png)

10. 返回浏览器窗口，查看更新的文本。 （如果看不到更改的文本，请刷新浏览器。）

    ![刷新浏览器窗口以查看更改的文本](../ide/media/csharp-aspnet-browser-page-about-changed.png)

11. 从工具栏选择“停止调试”按钮来停止调试。 （或者，按 Shift+F5 或从菜单栏选择“调试” > “停止调试”。）

   ![在工具栏上，单击“停止调试”按钮](../ide/media/csharp-aspnet-stop-debugging.png)

## <a name="next-steps"></a>后续步骤

恭喜你完成本教程！ 希望你已对 C#、ASP.NET Core 和 Visual Studio IDE 有了一定了解。 若要更加深入地了解，请继续学习下面的教程。

 > [!div class="nextstepaction"]
 > [ASP.NET Core MVC 和 Visual Studio 入门](/aspnet/core/tutorials/first-mvc-app/start-mvc?tabs=aspnetcore2x)
