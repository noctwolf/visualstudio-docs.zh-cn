---
title: 将发布到 Azure，通过导入发布设置
ms.custom: Create and import a publishing profile to deploy an application from Visual Studio to Azure App Service
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
ms.openlocfilehash: 88dc37e555f6ceb30584d4a1c17b96506219631a
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766735"
---
# <a name="publish-an-application-to-azure-app-service-by-importing-publish-settings-in-visual-studio"></a>发布到 Azure App Service 应用程序导入 Visual Studio 中发布设置

你可以使用**发布**工具导入发布设置，然后部署你的应用程序。 在本文中，我们将使用发布设置对 Azure App Service，但你可以使用类似的步骤来导入发布设置从[IIS](../deployment/tutorial-import-publish-settings-iis.md)。 在某些情况下，使用的发布设置配置文件可以是比手动配置部署到 Visual Studio 的每个安装的服务的速度更快。

这些步骤适用于 Visual Studio 中的 ASP.NET、 ASP.NET Core 和.NET Core 应用。 你还可以导入的发布设置[Python](/visualstudio/python/publishing-python-web-applications-to-azure-from-visual-studio)应用。 步骤与 Visual Studio 2017 版本 15.6 相对应。

在本教程中，你将：

> [!div class="checklist"]
> * 从 Azure App Service 中生成的发布设置文件
> * 将发布设置文件导入 Visual Studio
> * 将应用部署到 Azure App Service

发布设置文件 (*\*.publishsettings*) 不同于发布配置文件 (*\*.pubxml*) 在 Visual Studio 中创建。 发布设置文件创建的 Azure App Service，然后可以导入 Visual Studio。

> [!NOTE]
> 如果你只需复制 Visual Studio 发布配置文件 (*\*.pubxml*文件) 从 Visual Studio 的到另一个安装，您可以找到的发布配置文件，  *\<profilename\>.pubxml*中 *\\< projectname\>\Properties\PublishProfiles*用于托管的项目类型的文件夹。 对于网站，查看*\App_Data*文件夹。 发布配置文件是 MSBuild XML 文件。

## <a name="prerequisites"></a>系统必备

* 你必须安装的 Visual Studio 2017 和**ASP.NET**和。**NET Framework**开发工作负荷。 对于.NET Core 应用，你还需要。**NET 核心**工作负荷。

    如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)页免费安装。

* 创建 Azure 应用程序服务。 有关详细说明，请参阅[ASP.NET 核心 web 应用部署到 Azure 中使用 Visual Studio](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)。 

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>在 Visual Studio 中创建新的 ASP.NET 项目

1. 在计算机上运行 Visual Studio，选择**文件 > 新建项目**。

1. 下**Visual C#** 或**Visual Basic**，选择**Web**，然后在中间窗格中选择**ASP.NET Web 应用程序 (.NET Framework)** 或 (仅限 C#) **ASP.NET 核心 Web 应用程序**，然后单击**确定**。

    如果看不到指定的项目模板，请单击**打开 Visual Studio 安装程序**中的左窗格中的链接，**新项目**对话框。 Visual Studio 安装程序启动。 请参阅这篇文章，以标识所需的 Visual Studio 工作负荷，必须安装中的先决条件。

1. 选择**MVC** (.NET Framework) 或**Web 应用程序 （模型-视图-控制器）** （适用于.NET Core)，并确保**无身份验证**已选择，然后单击**确定**。

1. 键入的名称，例如**MyWebApp**单击**确定**。

    Visual Studio 随即创建项目。

1. 选择**生成 > 生成解决方案**以生成项目。

## <a name="create-the-publish-settings-file-in-azure-app-service"></a>在 Azure App Service 中创建的发布设置文件

1. 在 Azure 门户中，打开 Azure App Service。

1. 单击**Get 发布配置文件**并保存本地配置文件。

    ![获取发布配置文件](../deployment/media/tutorial-azure-app-service-get-publish-profile.png)

    与文件 *.publishsettings*已在你保存的位置中生成的文件扩展名。 下面的代码演示文件 （位于可读性更强的格式） 的部分示例。

    ```xml
    <publishData>
      <publishProfile
        profileName="DeployASPDotNetCore - Web Deploy"
        publishMethod="MSDeploy"
        publishUrl="deployaspdotnetcore.scm.azurewebsites.net:443"
        msdeploySite="DeployASPDotNetCore"
        userName="$DeployASPDotNetCore"
        userPWD="abcdefghijklmnopqrstuzwxyz"
        destinationAppUrl="http://deployaspdotnetcore20180508031824.azurewebsites.net"
        SQLServerDBConnectionString=""
        mySQLDBConnectionString=""
        hostingProviderForumLink=""
        controlPanelLink="http://windows.azure.com"
        webSystem="WebSites">
        <databases />
      </publishProfile>
    </publishData>
    ```
    通常，上面的 *.publishsettings 文件包含两个可以使用在 Visual Studio 中，一个用于部署使用 Web 部署，和一个使用 FTP 进行部署的发布配置文件。 上面的代码显示的 Web 部署的配置文件。 导入配置文件时，会将这两个配置文件导入更高版本。

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>导入 Visual Studio 中的发布设置和部署

[!INCLUDE [import publish settings](../deployment/includes/import-publish-settings-vs.md)]

## <a name="next-steps"></a>后续步骤

在本教程中中,，你将创建发布设置文件、 导入 Visual Studio 中，并部署到 Azure App Service 的 ASP.NET 应用程序。 你可能想要在 Visual Studio 中的发布选项的概述。

> [!div class="nextstepaction"]
> [初探部署](../deployment/deploying-applications-services-and-components.md)
