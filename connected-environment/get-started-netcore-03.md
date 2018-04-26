---
title: 在云中创建 .NET Core 开发环境（使用 Kubernetes 管理其中的容器）- 第 3 步 - 创建 ASP.NET Core Web 应用 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: douge
ms.openlocfilehash: 72c7df0a82b91f7b4665b8b7e2cecdfc2eea26cf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core"></a>开始使用 .NET Core 通连环境

上一步：[在 Azure 中创建 Kubernetes 开发环境](get-started-netcore-02.md)

## <a name="create-an-aspnet-core-web-app"></a>创建 ASP.NET Core Web 应用
如果已安装 [.NET Core](https://www.microsoft.com/net)，则可以在名为 `webfrontend` 的文件夹中快速创建 ASP.NET Core Web 应用。
```cmd
dotnet new mvc --name webfrontend
```

或者，可以导航到 https://github.com/Azure/vsce从 GitHub 下载示例代码，然后选择“克隆或下载”，将 GitHub 存储库下载到本地环境。 本指南所用代码位于 `vsce/samples/dotnetcore/getting-started/webfrontend` 中。

[!INCLUDE[](includes/vsce-init.md)]

[!INCLUDE[](includes/ensure-env-created.md)]

[!INCLUDE[](includes/build-and-run-in-k8s-cli.md)]

## <a name="update-a-content-file"></a>更新内容文件
通连环境不仅能让代码在 Kubernetes 中运行 - 还能让你在云中快速反复地查看代码更改在 Kubernetes 环境中的生效情况。

1. 找到文件 `./Views/Home/Index.cshtml` 并编辑 HTML。 例如，将读取 `<h2>Application uses</h2>` 的第 70 行更改为以下内容：`<h2>Hello k8s in Azure!</h2>`
1. 保存该文件。 稍后，终端窗口会出现消息，提示正在运行的容器中的文件已更新。
1. 转到浏览器并刷新页面。 应会看到网页上显示更新后的 HTML。

这是怎么回事？ 编辑内容文件（例如 HTML 和 CSS）无需在 .NET Core Web 应用中重新编译，因此活动 `vsce up` 命令会自动将任何已修改的内容文件同步到 Azure 中正在运行的容器中，从而提供查看内容编辑的快速方式。

## <a name="update-a-code-file"></a>更新代码文件
更新代码文件需要更多工作，因为 .NET Core 应用需要重新生成并生成更新后的应用程序二进制文件。

1. 在终端窗口中，按 `Ctrl+C`（停止 `vsce up`）。
1. 打开名为 `Controllers/HomeController.cs` 的代码文件，然后编辑“关于”页面上将显示的消息：`ViewData["Message"] = "Your application description page.";`
1. 保存该文件。
1. 在终端窗口中，运行 `vsce up`。 

这将重新生成容器映像并重新部署 Helm 图表。 要查看代码更改在正在运行的应用程序中的生效情况，请转到 Web 应用中的“关于”菜单。


但开发代码还有更快的方法，我们将在下一节中探讨。 
> [!div class="nextstepaction"]
> [在 Kubernetes 中调试容器](get-started-netcore-04.md)

