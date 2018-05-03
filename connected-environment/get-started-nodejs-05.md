---
title: 在云中创建 Node.js 开发环境（使用 Kubernetes 管理其中的容器）- 第 5 步 - 调用另一个容器 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: douge
ms.openlocfilehash: 89565869feec746aff75327b59ee7d0b466f26c1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>开始使用 Node.js 通连环境

上一步：[在 Kubernetes 中调试容器](get-started-nodejs-04.md)

在本节中，我们会再创建一个服务 `mywebapi`，并由 `webfrontend` 进行调用。 每个服务在不同的容器中运行。 然后，同时在这两个容器中进行调试。

![](media/multi-container.png)

## <a name="open-sample-code-for-mywebapi"></a>打开 mywebapi 的示例代码
在名为 `vsce/samples` 的文件夹下，应已有本指南所用 `mywebapi` 的示例代码（如果没有，请转到 https://github.com/Azure/vsce 并选择“克隆或下载”，下载 GitHub 存储库。）本节所用代码位于 `vsce/samples/nodejs/getting-started/mywebapi` 中。

## <a name="run-mywebapi"></a>运行 mywebapi
1. 在单独的 VS Code 窗口中打开文件夹 `mywebapi`。
1. 按 F5，然后等待服务生成和部署。 出现 VS Code 调试条时，即表示服务已准备就绪。
1. 记下终结点 URL，其格式如下：http://localhost:\<portnumber\>。 提示：VS Code 状态栏将显示可点击的 URL。 看起来容器是在本地运行，但实际上它是在 Azure 的开发环境中运行。 使用本地主机地址的原因是 `mywebapi` 尚未定义任何公共终结点，只能从 Kubernetes 实例中访问。 为方便起见，同时为了便于与本地计算机上的专用服务进行交互，通连环境会为 Azure 中运行的容器创建临时 SSH 隧道。
1. `mywebapi` 准备就绪后，打开浏览器并转到本地主机地址。 此时，`mywebapi` 服务会做出响应（“Hello from mywebapi”）。


## <a name="make-a-request-from-webfrontend-to-mywebapi"></a>从 webfrontend 向 mywebapi 发出请求
现在，请在 `webfrontend` 中编写代码，向 `mywebapi` 发出请求。
1. 切换到 `webfrontend` 的 VS Code 窗口。
1. 将这些代码行添加到 `server.js` 顶部：
```javascript
var request = require('request');
var propagateHeaders = require('./propagateHeaders');
```

3. 替换 `/api` GET 处理程序的代码。 处理请求时，会反过来调用 `mywebapi`，然后返回这两个服务的结果。

```javascript
app.get('/api', function (req, res) {
    request({
        uri: 'http://mywebapi',
        headers: propagateHeaders.from(req) // propagate headers to outgoing requests
    }, function (error, response, body) {
        res.send('Hello from webfrontend and ' + body);
    });
});
```

请注意 Kubernetes 的 DNS 服务发现如何用于将服务引用为 `http://mywebapi`。 开发环境中的代码运行方式与生产环境中相同。

上面的代码示例使用名为 `propagateHeaders` 的帮助程序模块。 此帮助程序在运行 `vsce init` 时已添加到代码文件夹中。 `propagateHeaders.from()` 函数将现有 http.IncomingMessage 对象中的特定标头传播到传出请求的标头对象中。 稍后会介绍这如何在团队方案中带来更高效的开发体验。


## <a name="debug-across-multiple-services"></a>跨多个服务进行调试
1. 此时，`mywebapi` 仍应在附加有调试器的情况下运行。 如果不是，请在 `mywebapi` 项目中按 F5。
1. 在默认 GET `/` 处理程序中设置断点。
1. 在 `webfrontend` 项目中，先设置断点，然后再向 `http://mywebapi` 发送 GET 请求。
1. 在 `webfrontend` 项目中按 F5。
1. 打开 Web 应用，并逐行执行两个服务中的代码。 Web 应用应显示两个服务串联的消息：“Hello from webfrontend and Hello from mywebapi”。


做得不错！ 现在便具有一个多容器应用程序，可分别开发和部署其中的每个容器。

> [!div class="nextstepaction"]
> [了解团队开发](get-started-nodejs-06.md)
