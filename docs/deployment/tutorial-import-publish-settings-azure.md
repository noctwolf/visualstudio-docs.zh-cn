---
title: 将发布到 Azure，通过导入发布设置
ms.description: Create and import a publishing profile to deploy an application from Visual Studio to Azure App Service
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
ms.openlocfilehash: 2b4b0e4ea963f20199267f32a8c87440c8cc350b
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38808316"
---
# <a name="publish-an-application-to-azure-app-service-by-importing-publish-settings-in-visual-studio"></a>通过导入发布到 Azure 应用服务应用程序在 Visual Studio 中发布设置

可以使用**发布**工具导入发布设置，然后将部署您的应用程序。 在本文中，我们将使用的 Azure 应用服务，发布设置，但你可以使用类似的步骤来导入发布设置从[IIS](../deployment/tutorial-import-publish-settings-iis.md)。 在某些情况下，使用的设置配置文件可以是比手动配置部署到每个安装的 Visual Studio 服务更快地发布。

这些步骤适用于 Visual Studio 中的 ASP.NET、 ASP.NET Core 和.NET Core 应用。 此外可以导入的发布设置[Python](../python/publishing-python-web-applications-to-azure-from-visual-studio.md)应用。 步骤与 Visual Studio 2017 版本 15.6 相对应。

在本教程中，你将：

> [!div class="checklist"]
> * 从 Azure 应用服务生成的发布设置文件
> * 导入 Visual Studio 的发布设置文件
> * 将应用部署到 Azure 应用服务

发布设置文件 (*\*.publishsettings*) 不同于发布配置文件 (*\*.pubxml*) 在 Visual Studio 中创建。 发布设置文件创建的 Azure 应用服务，然后可以导入 Visual Studio。

> [!NOTE]
> 如果您只需复制 Visual Studio 发布配置文件 (*\*.pubxml*文件) 从 Visual Studio 的到另一个安装，您可以找到发布配置文件，  *\<profilename\>.pubxml*，在 *\\< 项目名称\>\Properties\PublishProfiles*托管的项目类型的文件夹。 对于网站，查找下*\App_Data*文件夹。 发布配置文件是 MSBuild XML 文件。

## <a name="prerequisites"></a>系统必备

* 你必须安装 Visual Studio 2017 并**ASP.NET**和。**NET Framework**开发工作负载。 对于.NET Core 应用，你还需要。**NET 核心**工作负荷。

    如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)页免费安装。

* 创建 Azure 应用服务。 有关详细说明，请参阅[ASP.NET Core web 应用部署到 Azure 中使用 Visual Studio](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)。

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>在 Visual Studio 中创建新的 ASP.NET 项目

1. 在计算机上运行 Visual Studio，选择**文件** > **新项目**。

1. 下**Visual C#** 或**Visual Basic**，选择**Web**，然后在中间窗格中选择**ASP.NET Web 应用程序 (.NET Framework)** 或 (仅限 C#) **ASP.NET Core Web 应用程序**，然后单击**确定**。

    如果看不到指定的项目模板，请单击**打开 Visual Studio 安装程序**的左窗格中的链接**新项目**对话框。 Visual Studio 安装程序启动。 请参阅这篇文章，以标识所需的 Visual Studio 工作负荷，必须安装中的先决条件。

1. 选择**MVC** (.NET Framework) 或**Web 应用程序 （模型-视图-控制器）** （适用于.NET Core)，并确保**无身份验证**已选择，然后单击**确定**。

1. 键入一个名称，如**MyWebApp**然后单击**确定**。

    Visual Studio 随即创建项目。

1. 选择**构建** > **生成解决方案**以生成项目。

## <a name="create-the-publish-settings-file-in-azure-app-service"></a>在 Azure 应用服务中创建的发布设置文件

1. 在 Azure 门户中，打开 Azure 应用服务。

1. 单击**获取发布配置文件**并保存配置文件本地。

    ![获取发布配置文件](../deployment/media/tutorial-azure-app-service-get-publish-profile.png)

    包含的文件 *.publishsettings*您保存的位置中生成的文件扩展名。 下面的代码演示文件 （位于更可读格式） 的部分的示例。

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
    通常情况下，上面的 *.publishsettings 文件包含两个可以使用在 Visual Studio 中，一个用于将部署使用 Web 部署和一个使用 FTP 进行部署的发布配置文件。 前面的代码显示了 Web 部署配置文件。 导入配置文件时，将为这两个配置文件导入更高版本。

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>导入 Visual Studio 中的发布设置和部署

[!INCLUDE [import publish settings](../deployment/includes/import-publish-settings-vs.md)]

## <a name="next-steps"></a>后续步骤

在本教程中，创建发布设置文件、 导入到 Visual Studio 和 ASP.NET 应用部署到 Azure 应用服务。 您可能想要在 Visual Studio 中的发布选项的概述。

> [!div class="nextstepaction"]
> [初探部署](../deployment/deploying-applications-services-and-components.md)
