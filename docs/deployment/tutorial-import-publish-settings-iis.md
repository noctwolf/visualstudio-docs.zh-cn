---
title: 将发布到 IIS 通过导入发布设置
ms.custom: Create and import a publishing profile to deploy an application from Visual Studio to IIS
ms.date: 05/07/2018
ms.technology: vs-ide-deployment
ms.topic: tutorial
helpviewer_keywords:
- deployment, publish settings
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 02e6ae6e06daf43a6aec08097df2b37a21d2aaa3
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766666"
---
# <a name="publish-an-application-to-iis-by-importing-publish-settings-in-visual-studio"></a>发布到 IIS 应用程序导入 Visual Studio 中发布设置

你可以使用**发布**工具导入发布设置，然后部署你的应用程序。 在本文中，我们将使用发布设置的 IIS，但你可以使用类似的步骤来导入发布设置[Azure App Service](../deployment/tutorial-import-publish-settings-azure.md)。 在某些情况下，使用的发布设置配置文件可以是比手动配置每个安装的 Visual Studio 部署到 IIS 的速度更快。

这些步骤适用于 Visual Studio 中的 ASP.NET、 ASP.NET Core 和.NET Core 应用。 步骤与 Visual Studio 2017 版本 15.6 相对应。

在本教程中，你将：

> [!div class="checklist"]
> * 将 IIS 配置，以便你可以生成发布设置文件
> * 创建发布设置文件
> * 将发布设置文件导入 Visual Studio
> * 将应用程序部署到 IIS

发布设置文件 (*\*.publishsettings*) 不同于发布配置文件 (*\*.pubxml*) 在 Visual Studio 中创建。 发布设置文件创建由 IIS 或 Azure App Service 和可手动创建它，然后可以导入 Visual Studio。

> [!NOTE]
> 如果你只需复制 Visual Studio 发布配置文件 (\*.pubxml 文件) 从 Visual Studio 的到另一个安装，您可以找到的发布配置文件，  *\<profilename\>.pubxml*，在 *\\< projectname\>\Properties\PublishProfiles*用于托管的项目类型的文件夹。 对于网站，查看*\App_Data*文件夹。 发布配置文件是 MSBuild XML 文件。

## <a name="prerequisites"></a>系统必备

* 你必须安装的 Visual Studio 2017 和**ASP.NET**和 **.NET Framework**开发工作负荷。 对于.NET Core 应用，你还需要 **.NET Core**工作负荷。

    如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)页免费安装。

* 若要从 IIS 生成的发布设置文件，你必须运行 Windows Server 2012 或 Windows Server 2016 的计算机，并且你必须正确配置的 IIS Web 服务器角色。 此外必须安装 ASP.NET 4.5 或 ASP.NET Core。 有关 ASP.NET Core，请参阅[发布到 IIS](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration)。 为 ASP.NET 4.5，请参阅[IIS 8.0 使用 ASP.NET 3.5 和 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)。

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>在 Visual Studio 中创建新的 ASP.NET 项目

1. 在计算机上运行 Visual Studio，选择**文件 > 新建项目**。

1. 下**Visual C#** 或**Visual Basic**，选择**Web**，然后在中间窗格中选择**ASP.NET Web 应用程序 (.NET Framework)** 或 (仅限 C#) **ASP.NET Core Web 应用程序**，然后单击**确定**。

    如果看不到指定的项目模板，请单击**打开 Visual Studio 安装程序**中的左窗格中的链接，**新项目**对话框。 Visual Studio 安装程序启动。 请参阅这篇文章，以标识所需的 Visual Studio 工作负荷，必须安装中的先决条件。

1. 选择**MVC** (.NET Framework) 或**Web 应用程序 （模型-视图-控制器）** （适用于.NET Core)，并确保**无身份验证**已选择，然后单击**确定**。

1. 键入的名称，例如**MyWebApp**单击**确定**。

    Visual Studio 随即创建项目。

1. 选择**生成 > 生成解决方案**以生成项目。

## <a name="install-and-configure-web-deploy-on-windows-server"></a>安装和配置 Windows Server 上的 Web 部署

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

## <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>在 Windows Server 上的 IIS 中创建的发布设置文件

[!INCLUDE [create-publish-settings-iis](../deployment/includes/create-publish-settings-iis.md)]

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>导入 Visual Studio 中的发布设置和部署

[!INCLUDE [import-publish-settings](../deployment/includes/import-publish-settings-vs.md)]

应用程序已成功部署后，它应自动启动。 如果未启动从 Visual Studio，请在 IIS 中启动应用程序。 对于 ASP.NET Core，你需要确保应用程序池字段**DefaultAppPool**设置为**无托管代码**。

## <a name="next-steps"></a>后续步骤

在本教程中，创建发布设置文件、 导入 Visual Studio 和 ASP.NET 应用程序部署到 IIS。 你可能想要在 Visual Studio 中其他发布选项的概述。

> [!div class="nextstepaction"]
> [初探部署](../deployment/deploying-applications-services-and-components.md)
