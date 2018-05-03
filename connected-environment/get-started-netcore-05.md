---
title: 在云中创建 .NET Core 开发环境（使用 Kubernetes 管理其中的容器）- 第 5 步 - 调用另一个容器 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: douge
ms.openlocfilehash: 6ef3a79d0b79feae64adcaebe31daa48ba75ab75
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-net-core"></a>开始使用 .NET Core 通连环境

上一步：[在 Kubernetes 中调试容器](get-started-netcore-04.md)

在本节中，我们会再创建一个服务 `mywebapi`，并由 `webfrontend` 进行调用。 每个服务在不同的容器中运行。 然后，同时在这两个容器中进行调试。

![](media/multi-container.png)

## <a name="download-sample-code-for-mywebapi"></a>下载 mywebapi 的示例代码
为节约时间，我们从 GitHub 存储库下载示例代码。 转到 https://github.com/Azure/vsce 并选择“克隆或下载”，下载 GitHub 存储库。 本节所用代码位于 `vsce/samples/dotnetcore/getting-started/mywebapi` 中。


## <a name="run-mywebapi"></a>运行 mywebapi
1. 在单独的 VS Code 窗口中打开文件夹 `mywebapi`。
1. 按 F5，然后等待服务生成和部署。 出现 VS Code 调试条时，即表示服务已准备就绪。
1. 记下终结点 URL，其格式如下：http://localhost:\<portnumber\>。 提示：VS Code 状态栏将显示可点击的 URL。 看起来容器是在本地运行，但实际上它是在 Azure 的开发环境中运行。 使用本地主机地址的原因是 `mywebapi` 尚未定义任何公共终结点，只能从 Kubernetes 实例中访问。 为方便起见，同时为了便于与本地计算机上的专用服务进行交互，通连环境会为 Azure 中运行的容器创建临时 SSH 隧道。
1. `mywebapi` 准备就绪后，打开浏览器并转到本地主机地址。 在 URL 后追加 `/api/values`，以便调用 `ValuesController` 的默认 GET API。 
1. 如果已成功执行所有步骤，应能看到 `mywebapi` 服务的回应。


## <a name="make-a-request-from-webfrontend-to-mywebapi"></a>从 webfrontend 向 mywebapi 发出请求
现在，请在 `webfrontend` 中编写代码，向 `mywebapi` 发出请求。
1. 切换到 `webfrontend` 的 VS Code 窗口。
1. 替换 About 方法的代码：

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

以上代码示例也使用 `HeaderPropagatingHttpClient` 类。 此帮助程序类在运行 `vsce init` 时已添加到代码文件夹中。 `HeaderPropagatingHttpClient` 派生自已知的 `HttpClient` 类，它添加了另一功能，可将现有 ASP .NET HttpRequest 对象的特定标头传播到传出 HttpRequestMessage 对象。 稍后会介绍这如何在团队方案中带来更高效的开发体验。


## <a name="debug-across-multiple-services"></a>跨多个服务进行调试
1. 此时，`mywebapi` 仍应在附加有调试器的情况下运行。 如果不是，请在 `mywebapi` 项目中按 F5。
1. 在处理 `api/values/{id}` GET请求的 `Get(int id)` 方法中设置断点。
1. 在 `webfrontend` 项目中，先设置断点，然后再向 `mywebapi/api/values` 发送 GET 请求。
1. 在 `webfrontend` 项目中按 F5。
1. 调用 Web 应用，并逐行执行两个服务中的代码。
1. 在 Web 应用中，“关于”页会显示两个服务串联的消息：“Hello from webfrontend and Hello from mywebapi”。


做得不错！ 现在便具有一个多容器应用程序，可分别开发和部署其中的每个容器。

> [!div class="nextstepaction"]
> [了解团队开发](get-started-netcore-06.md)

