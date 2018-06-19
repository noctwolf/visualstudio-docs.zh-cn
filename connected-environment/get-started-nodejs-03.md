---
title: 在云中创建 Node.js 开发环境（使用 Kubernetes 管理其中的容器）- 第 3 步 - 创建 ASP.NET Web 应用 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: douge
ms.openlocfilehash: 34e1f07e173ccba6aab561fb4795abbe938e0127
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31890149"
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>开始使用 Node.js 通连环境

上一步：[在 Azure 中创建 Kubernetes 开发环境](get-started-nodejs-02.md)

## <a name="create-a-nodejs-web-app"></a>创建 Node.js Web 应用
要从 GitHub 下载示例代码，请导航到 https://github.com/Azure/vsce，然后选择“克隆或下载”，将 GitHub 存储库下载到本地环境。 本指南所用代码位于 `vsce/samples/nodejs/getting-started/webfrontend` 中。

[!INCLUDE[](includes/vsce-init.md)]

[!INCLUDE[](includes/ensure-env-created.md)]

[!INCLUDE[](includes/build-and-run-in-k8s-cli.md)]

## <a name="update-a-content-file"></a>更新内容文件
通连环境不仅能让代码在 Kubernetes 中运行 - 还能让你在云中快速反复地查看代码更改在 Kubernetes 环境中的生效情况。

1. 找到文件 `./public/index.html` 并编辑 HTML。 例如，将页面的背景色更改为蓝色阴影：

```html
<body style="background-color: #95B9C7; margin-left:10px; margin-right:10px;">
```

2. 保存该文件。 稍后，终端窗口会出现消息，提示正在运行的容器中的文件已更新。
1. 转到浏览器并刷新页面。 应看到颜色已更新。

这是怎么回事？ 编辑内容文件（例如 HTML 和 CSS）无需重启 Node.js 进程，因此活动 `vsce up` 命令会自动将任何已修改的内容文件直接同步到 Azure 中正在运行的容器中，提供查看内容编辑的快速方式。

### <a name="test-from-a-mobile-device"></a>从移动设备进行测试
如果在移动设备上打开 Web 应用，则会发现 UI 无法在小型设备上正确显示。

为解决此问题，我们将添加 `viewport` meta 标记：
1. 打开文件 `./public/index.html`
1. 在现有 `head` 元素中添加 `viewport` meta 标记：

```html
<head>
    <!-- Add this line -->
    <meta name="viewport" content="width=device-width, initial-scale=1">
</head>
```

1. 保存该文件。
1. 刷新设备浏览器。 现应看到正确呈现的 Web 应用。 

此示例说明，需在运行应用的设备上进行测试后才能发现某些问题。 借助 VS 通连环境，可快速迭代代码，并验证目标设备上的任何更改。

## <a name="update-a-code-file"></a>更新代码文件
更新服务器端代码文件需执行更多操作，因为需重启 Node.js 应用。

1. 在终端窗口中，按 `Ctrl+C`（停止 `vsce up`）。
1. 打开名为 `server.js` 的代码文件，然后编辑服务的 hello 消息： 

```javascript
res.send('Hello from webfrontend running in Azure!');
```

3. 保存该文件。
1. 在终端窗口中，运行 `vsce up`。 

这将重新生成容器映像并重新部署 Helm 图表。 重载浏览器页面，查看代码更改是否生效。


但开发代码还有更快的方法，我们将在下一节中探讨。 
> [!div class="nextstepaction"]
> [在 Kubernetes 中调试容器](get-started-nodejs-04.md)
