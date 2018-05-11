---
title: 将发布到 Azure App Service 的 Visual Studio |Microsoft 文档
ms.custom: ''
ms.date: 11/22/2017
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
ms.assetid: fc82b1f1-d342-4b82-9a44-590479f0a895
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- azure
ms.openlocfilehash: c5c172ff3ec3033b50815efdb0b4ee293853ab1e
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
---
# <a name="publish-an-aspnet-or-aspnet-core-app-to-azure-app-service-using-visual-studio"></a>向 Azure App Service 中使用 Visual Studio 发布 ASP.NET 或 ASP.NET Core 应用

你可以使用**发布**工具，用于将 ASP.NET、 ASP.NET Core、 Python、 Node.js 和.NET Core 应用发布到 Azure App Service。

如果你还没有 Azure 帐户，则可以[此处注册](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio)。

## <a name="prerequisites"></a>系统必备

* 你必须安装的 Visual Studio 2017 和**ASP.NET**和 **.NET Framework**开发工作负荷。 对于.NET Core 应用，你还需要 **.NET 核心**工作负荷。

    如果尚未安装 Visual Studio，请在[此处](http://www.visualstudio.com)免费安装。

## <a name="create-a-new-project"></a>创建新项目 

1. 在 Visual Studio 中，依次选择“文件”>“新建项目”。

1. 下**Visual C#** 或**Visual Basic**，选择**Web**，然后在中间窗格中选择**ASP.NET Web 应用程序 (.NET Framework)** 或 (仅限 C#) **ASP.NET 核心 Web 应用程序**，然后单击**确定**。

1. 选择**MVC** (或选择**Web 应用程序 （模型-视图-控制器）**为.NET Core)，请确保**无身份验证**已选择，然后单击**确定**.

1. 键入的名称，例如**MyWebApp**单击**确定**。

    Visual Studio 随即创建项目。

1. 选择**生成 > 生成解决方案**以生成项目。

## <a name="publish-to-azure-app-service"></a>发布到 Azure 应用服务

1. 在解决方案资源管理器中，右键单击项目，选择“发布”。

    ![选择发布](../deployment/media/quickstart-publish-aspnet.png "选择发布")

1. 如果你之前配置任何发布的配置文件，**发布**窗格中显示。 单击**创建新的配置文件**。

1. 在**选取发布目标**对话框框中，选择**App Service**。

    ![选择 Azure App Service](../deployment/media/quickstart-publish-azure.png "选择 Azure App Service")

1. 单击“发布” 。

    **创建 App Service**对话框随即出现。

    ![创建 App Service](../deployment/media/quickstart-publish-settings-app-service.png "创建 Azure App Service")
    
1. 如果不想要登录到 Visual Studio 中，登录，并默认应用程序服务设置然后填充字段。

    配置文件将发布的设置对话框随即打开。

    ![选择文件夹](../deployment/media/quickstart-publish-settings-web.png "选择文件夹")

    在此对话框中，你可以选择使用的订阅，选择或创建 Azure 资源组，等等。

1. 单击“创建” 。

    Visual Studio 将应用部署到你的 Azure 应用程序服务，并在浏览器中加载 web 应用程序。

    中的摘要**发布**窗格中，你看到新的 Azure App Service 的站点 URL。

## <a name="next-steps"></a>后续步骤

在本快速入门教程，您学习了如何使用 Visual Studio 来创建部署到 Azure 的发布配置文件。 你还可以配置发布配置文件通过导入发布设置从 Azure App Service。

> [!div class="nextstepaction"]
> [导入发布设置并部署到 Azure](tutorial-import-publish-settings-azure.md)
