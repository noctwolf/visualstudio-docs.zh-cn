---
title: 使用 Visual Studio 在云中创建 .NET Core 开发环境（使用 Kubernetes 管理其中的容器）- 第 5 步 - 调用另一个容器 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: douge
ms.openlocfilehash: ab3934e6f7f013dd21309dc8c98461983bdfe30a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31898422"
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>开始使用 .NET Core 和 Visual Studio 通连环境

上一步：[在 Kubernetes 中调试容器](get-started-netcore-visualstudio-04.md)

## <a name="call-another-container"></a>调用另一个容器
在本节中，我们会再创建一个服务 `mywebapi`，并由 `webfrontend` 进行调用。 每个服务在不同的容器中运行。 然后，同时在这两个容器中进行调试。

![](media/multi-container.png)

## <a name="download-sample-code-for-mywebapi"></a>下载 mywebapi 的示例代码
为节约时间，我们从 GitHub 存储库下载示例代码。 转到 https://github.com/Azure/vsce 并选择“克隆或下载”，下载 GitHub 存储库。 本节所用代码位于 `vsce/samples/dotnetcore/getting-started/mywebapi` 中。

## <a name="run-mywebapi"></a>运行 mywebapi
1. 在单独的 Visual Studio 窗口中打开项目 `mywebapi`。
1. 如之前为 `webfrontend` 执行的操作一样，从“启动设置”下拉列表中选择“适用于 AKS 的通连环境”。 这次无需创建新的开发环境，而是选择已创建的同一环境。 与之前一样，保留空间默认值 `mainline`，然后单击“确定”。 在输出窗口中，你可能会注意到 Visual Studio 开始在开发环境中“预热”这项新服务，以便在开始调试时加快速度，
1. 按 F5，然后等待服务生成和部署。 当 Visual Studio 状态栏变为橙色时，表示已准备就绪
1. 记下显示在“输出”窗口中“适用于 AKS 的通连环境”窗格的终结点 URL，其格式如下：http://localhost:\<portnumber\>。 看起来容器是在本地运行，但实际上它是在 Azure 的开发环境中运行。
1. 当 `mywebapi` 准备就绪后，打开浏览器转到本地主机地址，并将 `/api/values` 追加到 URL 以调用 `ValuesController` 的默认 GET API。 
1. 如果已成功执行所有步骤，应能看到 `mywebapi` 服务的回应，如下所示。

    ![](images/WebAPIResponse.png)

## <a name="make-a-request-from-webfrontend-to-mywebapi"></a>从 webfrontend 向 mywebapi 发出请求
现在，请在 `webfrontend` 中编写代码，向 `mywebapi` 发出请求。 切换到具有 `webfrontend` 项目的 Visual Studio 窗口。 在 `HomeController.cs` 文件中，将 About 方法的代码替换为以下代码：

 ```csharp
    public async Task<IActionResult> About()
    {
        ViewData["Message"] = "Hello from webfrontend";
        
        // Use HeaderPropagatingHttpClient instead of HttpClient so we can propagate
        // headers in the incoming request to any outgoing requests
        using (var client = new HeaderPropagatingHttpClient(this.Request))
        {
            // Call *mywebapi*, and display its response in the page
            var response = await client.GetAsync("http://mywebapi/api/values/1");
            ViewData["Message"] += " and " + await response.Content.ReadAsStringAsync();
        }
    
        return View();
    }

```

请注意 Kubernetes 的 DNS 服务发现如何用于将服务引用为 `http://mywebapi`。 开发环境中的代码运行方式与生产环境中相同。

以上代码示例也使用 `HeaderPropagatingHttpClient` 类。 此帮助程序类是在将项目配置为使用通连环境时添加到该项目中的 `HeaderPropagation.cs` 文件。 `HeaderPropagatingHttpClient` 派生自已知的 `HttpClient` 类，它添加了另一功能，可将现有 ASP .NET HttpRequest 对象的特定标头传播到传出 HttpRequestMessage 对象。 稍后会介绍这如何在团队方案中带来更高效的开发体验。

## <a name="debug-across-multiple-services"></a>跨多个服务进行调试
1. 此时，`mywebapi` 仍应在附加有调试器的情况下运行。 如果不是，请在 `mywebapi` 项目中按 F5。
1. 在 `ValuesController.cs` 文件内处理 `api/values/{id}` GET 请求的 `Get(int id)` 方法中设置断点。
1. 在已粘贴上述代码的 `webfrontend` 项目中，先设置断点，然后再向 `mywebapi/api/values` 发送 GET 请求。
1. 在 `webfrontend` 项目中按 F5。 Visual Studio 会再次打开浏览器，转到相应的本地主机端口，并显示 Web 应用。
1. 单击页面顶部的“关于”链接来触发 `webfrontend` 项目中的断点。 
1. 按 F10 以继续。 现在会触发 `mywebapi` 项目中的断点。
1. 按 F5 以继续，可返回到 `webfrontend` 项目的代码中。
1. 再次按 F5 可完成请求并在浏览器中返回一个页面。 在 Web 应用中，“关于”页会显示两个服务串联的消息：“Hello from webfrontend and Hello from mywebapi”。

做得不错！ 现在便具有一个多容器应用程序，可分别开发和部署其中的每个容器。

> [!div class="nextstepaction"]
> [了解团队开发](get-started-netcore-visualstudio-06.md)

