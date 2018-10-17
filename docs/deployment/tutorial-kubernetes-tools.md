---
title: Kubernetes 工具教程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2018
ms.technology: vs-ide-deployment
ms.topic: conceptual
author: ghogen
ms.author: ghogen
manager: douge
ms.workload:
- azure
ms.openlocfilehash: 079ae6affd5c495136d97a00eae2ddccfa2c9066
ms.sourcegitcommit: e680e8ac675f003ebcc8f8c86e27f54ff38da662
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2018
ms.locfileid: "49356777"
---
# <a name="get-started-with-visual-studio-kubernetes-tools"></a>开始使用 Visual Studio 的 Kubernetes 工具

Visual Studio Kubernetes 工具可帮助简化面向 Kubernetes 的容器化应用程序的开发。 Visual Studio 可以自动创建支持 Kubernetes 部署，如 Dockerfile 和 Helm 图表所需的配置即代码文件。 可以调试实时 Azure Kubernetes 服务 (AKS) 群集使用 Azure 开发人员空间中的代码，也可以直接发布到 AKS 群集从 Visual Studio 内部。

本教程介绍如何使用 Visual Studio 将 Kubernetes 支持添加到项目并将发布到 AKS。 如果您不感兴趣使用的主要[Azure 开发人员空格](http://aka.ms/get-azds)若要调试和测试项目在 AKS 中运行，可以跳转到[Azure 开发人员空格教程](https://docs.microsoft.com/azure/dev-spaces/get-started-netcore-visualstudio)改为。

## <a name="prerequisites"></a>系统必备

若要利用这一新功能，你将需要：

- 最新版[Visual Studio 2017](https://visualstudio.microsoft.com/download)与*ASP.NET 和 web 开发*工作负荷。

- [用于 Visual Studio 的 Kubernetes 工具](https://aka.ms/get-vsk8stools)、 作为单独的下载可用。

- [适用于 Windows 的 docker](https://store.docker.com/editions/community/docker-ce-desktop-windows)开发工作站上安装 （即，其中你运行 Visual Studio），如果你想要生成 Docker 映像，调试本地运行的 Docker 容器或发布到 AKS。 (Docker 是*不*所需的生成和调试在 AKS 使用 Azure 开发人员空间中的 Docker 容器。)

- 如果你想要从 Visual Studio 发布到 AKS (*不*所需的调试在 AKS 使用 Azure 开发人员空间中):

    1.  [AKS 发布工具](https://aka.ms/get-vsk8spublish)、 作为单独的下载可用。

    1.  Azure Kubernetes 服务群集。 有关详细信息，请参阅[创建 AKS 群集](/azure/aks/kubernetes-walkthrough-portal#create-aks-cluster)。 请务必[连接到群集](/azure/aks/kubernetes-walkthrough#connect-to-the-cluster)从你的开发工作站。

    1.  Helm CLI 安装在开发工作站上。 有关详细信息请参阅[安装 Helm](https://github.com/kubernetes/helm/blob/master/docs/install.md)。

    1.  通过使用针对你的 AKS 群集配置 helm`helm init`命令。 有关如何执行此操作的详细信息，请参阅[如何配置 Helm](/azure/aks/kubernetes-helm#configure-helm)。

## <a name="create-a-new-kubernetes-project"></a>创建新的 Kubernetes 项目

安装了相应工具后，启动 Visual Studio 并创建一个新项目。 下**云**，选择**适用于 Kubernetes 的容器应用程序**项目类型。 选择此项目类型，然后选择**确定**。

![创建一个新的 Kubernetes 应用程序项目的屏幕截图](media/k8s-tools-new-k8s-app.png)

您然后可以选择哪种类型的 ASP.NET Core web 应用程序创建。 选择**Web 应用程序**，然后选择**确定**。 常用**启用 Docker 支持**选项没有出现在该对话框中。  适用于 Kubernetes 的容器应用程序的默认情况下被启用 docker 支持。

![Web 应用所选内容的屏幕截图](media/k8s-tools-web-app-selection-screen.png)

## <a name="add-kubernetes-support-to-an-existing-project"></a>将 Kubernetes 支持添加到现有项目

或者，可以将 Kubernetes 支持添加到现有的 ASP.NET Core web 应用程序项目。 若要执行此操作，右键单击项目，然后选择**外** > **容器业务流程协调程序支持**。

![屏幕截图的添加容器业务流程协调程序菜单项](media/k8s-tools-add-container-orchestrator.png)

在对话框中，选择"Kubernetes/Helm"并选择**确定**。

![屏幕截图的添加容器业务流程协调程序对话框](media/k8s-tools-add-container-orchestrator-dialog-box.PNG)

## <a name="what-visual-studio-creates-for-you"></a>Visual Studio 为您创建

创建一个新后**适用于 Kubernetes 的容器应用程序**项目或将 Kubernetes 容器业务流程协调程序支持添加到现有项目，请参阅你的项目中的某些其他文件，可协助将部署到 Kubernetes。

![屏幕截图的解决方案资源管理器后添加容器业务流程协调程序支持](media/k8s-tools-solution-explorer.png)

添加的文件是：

- Dockerfile，以便您可以生成 Docker 容器映像托管此 web 应用程序。 如您将看到，Visual Studio 工具将利用此 Dockerfile 时调试和部署到 Kubernetes。 如果想要直接使用 Docker 映像，可以在 Dockerfile 上右键单击并选择**生成 Docker 映像**。

   ![屏幕快照生成 Docker 映像的选项](media/k8s-tools-build-docker-image.png)

- 一个 Helm 图表和一个*图表*文件夹。 这些 yaml 文件构成了为应用程序，可用来将其部署到 Kubernetes Helm 图表。 Helm 的详细信息，请参阅[ https://www.helm.sh ](https://www.helm.sh)。

- *azds.yaml*。 这包含 Azure 开发人员空格，这提供了快速、 迭代的调试体验，在 Azure Kubernetes 服务中的设置。 有关详细信息，请参阅[Azure 开发人员空间文档](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces)。

## <a name="publish-to-azure-kubernetes-service-aks"></a>发布到 Azure Kubernetes 服务 (AKS)

与所有这些文件后，可用于 Visual Studio IDE 中编写和调试应用程序代码中，只需像往常一样。 此外可以使用[Azure 开发人员空格](http://aka.ms/get-azds)快速运行和调试你的代码在 AKS 群集中实时运行。 有关详细信息，请参阅[Azure 开发人员空格教程](https://docs.microsoft.com/azure/dev-spaces/get-started-netcore-visualstudio)

一旦您具有运行所需的方式的代码可以直接从 Visual Studio 发布到 AKS 群集。

若要执行此操作，首先需要仔细检查，你已安装的所有内容中所述[先决条件](#prerequisites)部分下的项发布到 AKS，并通过提供的链接中的所有命令行步骤运行。 然后，设置发布到 Azure 容器注册表 (ACR) 的容器映像的发布配置文件。 然后 AKS 可以从 ACR 提取容器映像并将其部署到群集。

1. 在中**解决方案资源管理器**，右键单击你*项目*，然后选择**发布**。

   ![屏幕快照的发布菜单项](media/k8s-tools-publish-project.png)

1. 在中**发布**屏幕上，选择**容器注册表**作为发布目标，并按照提示来选择容器注册表。 如果还没有容器注册表，选择**创建新的 Azure 容器注册表**若要从 Visual Studio 中创建一个。 有关详细信息，请参阅[将容器发布到 Azure 容器注册表](#publish-your-container-to-azure-container-registry)。

   ![选取发布目标屏幕的屏幕截图](media/k8s-tools-publish-to-acr.png)

1. 返回在解决方案资源管理器，右键单击你*解决方案*然后单击**发布到 Azure AKS**。

   ![屏幕快照的发布到 Azure AKS 菜单项](media/k8s-tools-publish-solution.png)

1. 选择你的订阅和 AKS 群集，以及 ACR 发布刚创建的配置文件。 然后单击“确定” 。

   ![屏幕快照的发布到 AKS 屏幕](media/k8s-tools-publish-to-aks.png)

   将进入**发布到 Azure AKS**屏幕。

1.  选择**配置 Helm**链接以更新用来在服务器上安装 Helm 图表的命令行。

   ![配置 Helm 屏幕快照链接](media/k8s-tools-configure-helm.png)

   更新命令行是很有用，如果你想要指定，例如不同的 Kubernetes 上下文或图表名称的自定义命令行参数。

   ![屏幕截图的 Helm 配置屏幕](media/k8s-tools-helm-configure-screen.png)

1. 若要部署准备就绪后，单击**发布**按钮以发布应用程序到 AKS。

   ![发布到 Azure AKS 屏幕的屏幕截图](media/k8s-tools-publish-screen.png)

祝贺你！ 现在可以为所有 Kubernetes 应用程序开发使用 Visual Studio 的完整功能。

## <a name="next-steps"></a>后续步骤

通过阅读了解有关 Azure 上的 Kubernetes 开发的详细信息[AKS 文档](/azure/aks)。

通过阅读了解有关 Azure 开发人员空间的详细信息[Azure 开发人员空间文档](http://aka.ms/get-azds)
