---
title: 使用 Visual Studio 在云中创建 .NET Core 开发环境（使用 Kubernetes 管理其中的容器）- 第 4 步 - 在 Kubernetes 中调试容器 | Microsoft Docs
author: johnsta
ms.author: johnsta
ms.date: 02/20/2018
ms.topic: get-started-article
ms.technology: vsce-kubernetes
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: ghogen
ms.openlocfilehash: 9b3aa6b0f710707800ea9a1f0533b0c37681ea05
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>开始使用 .NET Core 和 Visual Studio 通连环境

上一步：[在 Azure 中创建开发环境](get-started-netcore-visualstudio-03.md)

## <a name="debug-a-container-in-kubernetes"></a>在 Kubernetes 中调试容器
成功创建开发环境后，便可以调试应用程序。 在代码中设置一个断点，例如设置在 `Message` 变量所在的 `HomeController.cs` 文件中的第 20 行上。 按 F5 启动调试。 

Visual Studio 将与开发环境进行通信来生成和部署应用程序，然后在运行 Web 应用的情况下打开浏览器。 看起来容器是在本地运行，但实际上它是在 Azure 的开发环境中运行。 使用本地主机地址的原因是通连环境创建了通向在 Azure 中运行的容器的临时 SSH 隧道。

单击页面顶部的“关于”链接来触发断点。 你对调试信息拥有完全访问权限，可像在本地执行代码一样进行操作，比如调用堆栈、局部变量和异常信息等。

> [!div class="nextstepaction"]
> [调用另一个容器](get-started-netcore-visualstudio-05.md)