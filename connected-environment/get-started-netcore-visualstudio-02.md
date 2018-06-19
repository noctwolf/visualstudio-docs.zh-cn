---
title: 使用 Visual Studio 在云中创建 .NET Core 开发环境（使用 Kubernetes 管理其中的容器）- 第 2 步 - 创建 ASP.NET Web 应用 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: douge
ms.openlocfilehash: d28661e8f252201a200c7e5f254d337edb6fe9e2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31887981"
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>开始使用 .NET Core 和 Visual Studio 通连环境

上一步：[安装工具](get-started-netcore-visualstudio-01.md)

## <a name="create-an-aspnet-web-app"></a>创建 ASP.NET Web 应用
从 Visual Studio 2017 中创建一个新项目，此项目当前必须是 ASP.NET Core Web 应用程序。 将项目命名为“webfrontend”。

![](images/NewProjectDialog1.png)

选择“Web 应用程序(模型 - 视图 - 控制器)”模板，并确保在对话框顶部的两个下拉列表中分别选择“.NET Core”和“ASP.NET Core 2.0”。 单击“确定”，创建项目。

![](images/NewProjectDialog2.png)

> [!div class="nextstepaction"]
> [在 Azure 中创建开发环境](get-started-netcore-visualstudio-03.md)