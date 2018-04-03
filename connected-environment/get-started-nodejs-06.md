---
title: 在云中创建 Node.js 开发环境（使用 Kubernetes 管理其中的容器）- 第 6 步 - 了解团队开发 | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: ghogen
ms.openlocfilehash: 4db1d71c96da29a06884e562a277a7ca427910d4
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-nodejs"></a>开始使用 Node.js 通连环境

上一步：[调用在单独容器中运行的服务](get-started-nodejs-05.md)

[!INCLUDE[](includes/team-development-1.md)]

我们来看一下实际的效果：
1. 转到 `mywebapi` 的 VS Code 窗口，并对默认 GET `/` 处理程序进行代码编辑，例如：

```javascript
app.get('/', function (req, res) {
    res.send('mywebapi now says something new');
});
```

[!INCLUDE[](includes/team-development-2.md)]

> [!div class="nextstepaction"]
> [下一篇](get-started-nodejs-07.md)

