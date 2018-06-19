---
title: 使用 Visual Studio 在云中创建 .NET Core 开发环境（使用 Kubernetes 管理其中的容器）- 第 3 步 - 创建 Kubernetes 开发环境 | Microsoft Docs
author: ghogen
ms.author: ghogen
ms.date: 02/20/2018
ms.topic: tutorial
ms.prod: visual-studio-dev15
ms.technology: vs-azure
description: 使用 Azure 上的容器和微服务快速开发 Kubernetes
keywords: Docker, Kubernetes, Azure, AKS, Azure 容器服务, 容器
manager: douge
ms.openlocfilehash: 6226340b1744e95bbb375d47213ae00bb9e76565
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31884380"
---
# <a name="get-started-on-connected-environment-with-net-core-and-visual-studio"></a>开始使用 .NET Core 和 Visual Studio 通连环境

上一步：[创建 ASP.NET Web 应用](get-started-netcore-visualstudio-02.md)

## <a name="create-a-dev-environment-in-azure"></a>在 Azure 中创建开发环境
借助通连环境，可创建基于 Kubernetes 的开发环境，这些开发环境由 Azure 完全托管，并针对开发进行了优化。 打开刚刚创建的项目，从“启动设置”下拉列表中选择“适用于 AKS 的通连环境”，如下所示。

![](images/LaunchSettings.png)

在随后显示的对话框中，确保已使用适当的帐户登录，然后选择现有开发环境或选择“<新建适用于 AKS 的通连环境...>”，创建一个新环境。

![](images/ConnectedEnvDialog.png)

可使用提供的默认值，也可根据需要进行调整。 正确设置值后，单击“确定”。

![](images/NewEnvDialog.png)

返回上一个对话框，暂时将“空间”下拉菜单保留为默认值 `mainline`，稍后我们将对此进行详细讨论。 选中“可公开访问”复选框，以便可通过公共终结点访问该 Web 应用。 这不是必选项，但对于本演练后面部分介绍的一些概念有所帮助。 但不用担心，无论是否勾选此项，都可使用 Visual Studio 调试网站。

![](images/ConnectedEnvDialog2.png)

单击“确定”，选择或创建开发环境。 后台任务随即启动并完成此操作，完成这一过程需花费几分钟时间。 将光标悬停在状态栏左下角的“后台任务”图标上，可查看是否完成创建（如下所示）。

![](images/BackgroundTasks.png)

> [!Note]
在成功创建开发环境之前，无法调试应用程序。

## <a name="look-at-the-files-added-to-project"></a>查看添加到项目的文件
在等待创建开发环境期间，可以查看选择使用开发环境时添加到项目的文件。

首先，可看到已添加名为 `charts` 的文件夹，且该文件夹中已搭建应用程序 [Helm 图表](https://docs.helm.sh) 的基架。 这些文件用于将应用程序部署到开发环境。

可看到已添加一个名为 `Dockerfile` 的文件。 将应用程序打包为标准 Docker 格式时需要使用此文件中的信息。 还创建了一个 `HeaderPropagation.cs` 文件，稍后的演练中会介绍这个文件。 

最后，可看到一个名为 `vsce.yaml` 的文件，其中包含开发环境所需的配置信息，例如是否可通过公共终结点访问应用程序。

![](images/ProjectFiles.png)

> [!div class="nextstepaction"]
> [在 Kubernetes 中调试容器](get-started-netcore-visualstudio-04.md)