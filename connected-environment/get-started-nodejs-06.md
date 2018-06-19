---
title: 在云中创建 Node.js 开发环境（使用 Kubernetes 管理其中的容器）- 第 6 步 - 了解团队开发 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: douge
ms.openlocfilehash: 6a17dfc3eeebccf1508ea3f69aecb53d067de7af
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31883574"
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

