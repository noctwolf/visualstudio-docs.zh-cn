---
title: 在云中创建 .NET Core 开发环境（使用 Kubernetes 管理其中的容器）- 第 6 步 - 了解团队开发 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: douge
ms.openlocfilehash: 4da5051b760a12f8fd8837072ada44c8c5a9b239
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31884338"
---
# <a name="get-started-on-connected-environment-with-net-core"></a>开始使用 .NET Core 通连环境

上一步：[调用另一个容器](get-started-netcore-05.md)

[!INCLUDE[](includes/team-development-1.md)]

我们来看一下实际的效果：
1. 转到 `mywebapi` 的 VS Code 窗口，并对 `string Get(int id)` 方法进行代码编辑，例如：

```csharp
[HttpGet("{id}")]
public string Get(int id)
{
    return "mywebapi now says something new";
}
```

[!INCLUDE[](includes/team-development-2.md)]

> [!div class="nextstepaction"]
> [下一篇](get-started-netcore-07.md)
