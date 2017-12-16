---
title: "将发布到 Azure App Service 的 Visual Studio |Microsoft 文档"
ms.custom: 
ms.date: 11/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: quickstart
helpviewer_keywords: deployment, website
ms.assetid: fc82b1f1-d342-4b82-9a44-590479f0a895
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0c1fa8867c4f9ab46b50f0b2a144970d772cbd71
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="publish-an-aspnet-or-aspnet-core-app-to-azure-app-service-using-visual-studio"></a>向 Azure App Service 中使用 Visual Studio 发布 ASP.NET 或 ASP.NET Core 应用

你可以使用**发布**工具，用于将 ASP.NET、 ASP.NET Core、 Python、 Node.js 和.NET Core 应用发布到 Azure App Service。

如果你还没有 Azure 帐户，则可以[此处注册](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio)。

## <a name="create-a-new-project"></a>创建新项目 

1. 在 Visual Studio 中，选择**文件 > 新建项目**。

1. 下**Visual C#**或**Visual Basic**，选择**Web**，然后在中间窗格中选择**ASP.NET Web 应用程序 (.NET Framework)**或 (仅限 C#) **ASP.NET 核心 Web 应用程序**，然后单击**确定**。

1. 选择**MVC**，请确保**无身份验证**已选择，然后单击**确定**。

1. 键入的名称，例如**MyWebApp**单击**确定**。

    Visual Studio 创建项目。

1. 选择**生成 > 生成解决方案**以生成项目。

## <a name="publish-to-azure-app-service"></a>发布到 Azure 应用服务

1. 在解决方案资源管理器，右键单击该项目并选择**发布**。

    ![选择发布](../deployment/media/quickstart-publish-aspnet.png "选择发布")

1. 在**发布**窗格中，选择**Microsoft Azure App Service**。

    ![选择 Azure App Service](../deployment/media/quickstart-publish-azure.png "选择 Azure App Service")

1. 单击“发布” 。

    **创建 App Service**对话框随即出现。

    ![创建 App Service](../deployment/media/quickstart-publish-settings-app-service.png "创建 Azure App Service")
    
1. 如果不想要登录到 Visual Studio 中，登录，并默认应用程序服务设置然后填充字段。

    配置文件将发布的设置对话框随即打开。

    ![选择文件夹](../deployment/media/quickstart-publish-settings-web.png "选择文件夹")

    在此对话框中，你可以选择使用的订阅，选择或创建 Azure 资源组，等等。

1. 单击 **“创建”**。

    Visual Studio 将应用部署到你的 Azure 应用程序服务，并在浏览器中加载 web 应用程序。

    中的摘要**发布**窗格中，你看到新的 Azure App Service 的站点 URL。

## <a name="next-steps"></a>后续步骤

- [将 ASP.NET Core 应用程序部署到 Azure](https://docs.microsoft.com/en-us/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)
- [ASP.NET 核心到具有 Git 的 Azure 的连续部署](https://docs.microsoft.com/en-us/aspnet/core/publishing/azure-continuous-deployment)
