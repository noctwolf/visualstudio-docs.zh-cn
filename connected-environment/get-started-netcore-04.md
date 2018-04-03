---
title: 在云中创建 .NET Core 开发环境（使用 Kubernetes 管理其中的容器）- 第 4 步 - 在 Kubernetes 中调试容器 | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: ghogen
ms.openlocfilehash: f06489194f70a3e7e617f4022917cd1d4a96337f
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-net-core"></a>开始使用 .NET Core 通连环境
 
上一步：[创建 ASP.NET Core Web 应用](get-started-netcore-03.md)

[!INCLUDE[](includes/debug-intro.md)]

[!INCLUDE[](includes/init-debug-assets-vscode.md)]


## <a name="select-the-vsce-debug-configuration"></a>选择 VSCE 调试配置
1. 要打开调试视图，请单击 VS Code 一侧“活动栏”中的调试图标。
1. 选择“.NET Core Launch (VSCE)”作为活动调试配置。

![](media/debug-configuration.png)

> [!Note]
> 如果在命令面板中看不到任何通连环境命令，请确保[安装了适用于通连环境的 VS Code 扩展](get-started-netcore-01.md#get-kubernetes-debugging-for-vs-code) 。


## <a name="debug-the-container-in-kubernetes"></a>在 Kubernetes 中调试容器
按 F5 在 Kubernetes 中调试代码。

与 `up` 命令一样，代码将同步到开发环境，同时生成容器并将其部署到 Kubernetes。 当然，这一次调试程序已附加到远程容器。

[!INCLUDE[](includes/tip-vscode-status-bar-url.md)]

在服务器端代码文件中设置断点，例如在 `Controllers/HomeController.cs` 源文件的 `Index()` 函数中设置。 刷新浏览器页面会命中断点。

你对调试信息拥有完全访问权限，可像在本地执行代码一样进行操作，比如调用堆栈、局部变量和异常信息等。

## <a name="edit-code-and-refresh"></a>编辑代码和刷新
在调试程序处于活动状态时，编辑代码。 例如，修改 `Controllers/HomeController.cs` 中“关于”页面的消息。 

```csharp
public IActionResult About()
{
    ViewData["Message"] = "My custom message in the About page.";
    return View();
}
```

保存该文件，然后在“调试操作窗格”中，单击“刷新”按钮。 

![](media/debug-action-refresh.png)

通连环境将以增量方式在现有容器中重新编译代码，加快编辑/调试循环，而不是在每次编辑代码时重新生成和重新部署新的容器映像，这往往需要相当长的时间。

在浏览器中刷新 Web 应用，然后转到“关于”页面。 应可看到自定义消息出现在 UI 中。

现在你已了解这种可以快速迭代代码并直接在 Kubernetes 中进行调试的方法。 接下来将介绍如何创建并调用第二个容器。

> [!div class="nextstepaction"]
> [调用在单独容器中运行的服务](get-started-netcore-05.md)
