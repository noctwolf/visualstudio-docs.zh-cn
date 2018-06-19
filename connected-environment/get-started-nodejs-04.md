---
title: 在云中创建 Node.js 开发环境（使用 Kubernetes 管理其中的容器）- 第 4 步 - 在 Kubernetes 中调试容器 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: douge
ms.openlocfilehash: 2d1ec5fe0436b394083a247faa4519505aa21ceb
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31888540"
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>开始使用 Node.js 通连环境

上一步：[在 Kubernetes 中创建 Node.js 容器](get-started-nodejs-03.md)

[!INCLUDE[](includes/debug-intro.md)]

[!INCLUDE[](includes/init-debug-assets-vscode.md)]


## <a name="select-the-vsce-debug-configuration"></a>选择 VSCE 调试配置
1. 要打开调试视图，请单击 VS Code 一侧“活动栏”中的调试图标。
1. 选择“启动程序(VSCE)”作为活动调试配置。

![](media/debug-configuration-nodejs.png)

> [!Note]
> 如果在命令面板中看不到任何通连环境命令，请确保[安装了适用于通连环境的 VS Code 扩展](get-started-nodejs-01.md#get-kubernetes-debugging-for-vs-code) 。

## <a name="debug-the-container-in-kubernetes"></a>在 Kubernetes 中调试容器
按 F5 在 Kubernetes 中调试代码！

与 `up` 命令类似，代码在调试开始时同步到开发环境，同时生成容器并将其部署到 Kubernetes。 当然，这一次调试程序已附加到远程容器。

[!INCLUDE[](includes/tip-vscode-status-bar-url.md)]

在服务器端代码文件中设置断点，例如在 `server.js` 的 `app.get('/api'...` 中设置。 刷新浏览器页面，或按“再说一次”按钮，应点击断点并逐行执行代码。

你对调试信息拥有完全访问权限，可像在本地执行代码一样进行操作，比如调用堆栈、局部变量和异常信息等。

## <a name="edit-code-and-refresh-the-debug-session"></a>编辑代码并刷新调试会话
在激活调试程序后编辑代码。例如，再次修改 hello 消息：

```javascript
app.get('/api', function (req, res) {
    res.send('**** Hello from webfrontend running in Azure! ****');
});
```

保存该文件，然后在“调试操作窗格”中，单击“刷新”按钮。 

![](media/debug-action-refresh-nodejs.png)

通连环境将在调试会话期间重启 Node.js 进程，加快编辑/调试循环，而不是在每次编辑代码时重新生成和重新部署新的容器映像，这往往需要相当长的时间。

刷新浏览器中的 Web 应用，或者按“再说一次”按钮。 应可看到自定义消息出现在 UI 中。


## <a name="use-nodemon-to-develop-even-faster"></a>使用 NodeMon 加快开发速度
Nodemon 是 Node.js 开发人员用于快速开发的常用工具。 开发人员通常会将其 Node 项目配置为包含 nodemon 监视文件更改并自动重启服务器进程，而不是在每次编辑服务器端代码时手动重启 Node 进程。 使用这种工作方式，开发人员编辑代码后只需刷新浏览器即可。

通连环境旨在让用户能够使用与在本地开发时相同的高效开发流程。 为说明这一点，我们将示例 `webfrontend` 项目配置为使用 nodemon（它在 `package.json` 中配置为开发依赖项）。

请尝试如下方法：
1. 停止 VS Code 调试程序。
1. 单击 VS Code 一侧“活动栏”中的调试图标。 
1. 选择“附加(VSCE)”作为活动调试配置。
1. 按 F5。

在此配置中，容器配置为启动 nodemon。 编辑服务器代码后，nodemon 自动重启 Node 进程，与在本地开发时一样。 
1. 在 `server.js` 中再次编辑 hello 消息，然后保存该文件。
1. 刷新浏览器，或单击“再说一次”按钮，查看更改是否生效！

现在你已了解这种可以快速迭代代码并直接在 Kubernetes 中进行调试的方法。 接下来将介绍如何创建并调用第二个容器。

> [!div class="nextstepaction"]
> [调用在单独容器中运行的服务](get-started-nodejs-05.md)

