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
ms.openlocfilehash: b023349454f71835e13e7cc891b8be92b90c153f
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2018
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
> 如果你只需复制 Visual Studio 发布配置文件 (\*.pubxml 文件) 从 Visual Studio 的到另一个安装，您可以找到的发布配置文件，  *\<profilename\>.pubxml*，在 *\\< projectname\>\Properties\PublishProfiles*用于托管的项目类型的文件夹。 对于网站，查看 *\App_Data*文件夹。 发布配置文件是 MSBuild XML 文件。

## <a name="prerequisites"></a>系统必备

* 你必须安装 Visual Studio 和**ASP.NET**和 **.NET Framework**开发工作负荷。 对于.NET Core 应用，你还需要 **.NET 核心**工作负荷。

    如果尚未安装 Visual Studio，请在[此处](http://www.visualstudio.com)免费安装。

    在 Visual Studio 2017 基于这篇文章中的步骤

* 若要从 IIS 生成的发布设置文件，你必须正确配置的 IIS 8.0 Web 服务器角色与运行 Windows Server 2012 的计算机和安装 ASP.NET 4.5 或 ASP.NET Core。 有关 ASP.NET 核心，请参阅[发布到 IIS](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration)。 为 ASP.NET 4.5，请参阅[IIS 8.0 使用 ASP.NET 3.5 和 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)。

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>在 Visual Studio 中创建新的 ASP.NET 项目

1. 在计算机上运行 Visual Studio，选择**文件 > 新建项目**。

1. 下**Visual C#** 或**Visual Basic**，选择**Web**，然后在中间窗格中选择**ASP.NET Web 应用程序 (.NET Framework)** 或 (仅限 C#) **ASP.NET 核心 Web 应用程序**，然后单击**确定**。

    如果看不到指定的项目模板，请单击**打开 Visual Studio 安装程序**中的左窗格中的链接，**新项目**对话框。 Visual Studio 安装程序启动。 请参阅这篇文章，以标识所需的 Visual Studio 工作负荷，必须安装中的先决条件。

1. 选择**MVC** (.NET Framework) 或**Web 应用程序 （模型-视图-控制器）** （适用于.NET Core)，并确保**无身份验证**已选择，然后单击**确定**。

1. 键入的名称，例如**MyWebApp**单击**确定**。

    Visual Studio 随即创建项目。

1. 选择**生成 > 生成解决方案**以生成项目。

## <a name="install-and-configure-web-deploy-on-windows-server"></a>安装和配置 Windows Server 上的 Web 部署

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

## <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>在 Windows Server 上的 IIS 中创建的发布设置文件

1. 在 IIS 中，右键单击**Default Web Site**，选择**部署** > **配置 Web 部署发布**。

    ![配置 Web 部署配置](../deployment/media/tutorial-configure-web-deploy-publishing.png)

1. 在**配置 Web 部署发布**对话框框中，检查设置。

1. 单击**安装**。

    在**结果**面板中，输出所示的访问权限已授予指定的用户，并与文件 *.publishsettings*已在中所示的位置中生成的文件扩展名对话框。

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <publishData>
      <publishProfile
        publishUrl="https://myhostname:8172/msdeploy.axd"
        msdeploySite="Default Web Site"
        destinationAppUrl="http://myhostname:80/"
        mySQLDBConnectionString=""
        SQLServerDBConnectionString=""
        profileName="Default Settings"
        publishMethod="MSDeploy"
        userName="myhostname\myusername" />
    </publishData>
    ```

    根据您的 Windows Server 和 IIS 配置，你将看到不同的值。 以下是有关你看到的值的一些详细信息：

    * *Msdeploy.axd*文件中引用`publishUrl`属性是动态生成 HTTP 处理程序文件用于 Web 部署。 (用于测试目的，`http://myhostname:8172`也将通常工作。)
    * `publishUrl`端口通常设置为端口 8172，这是默认值用于 Web 部署。
    * `destinationAppUrl`端口通常设置为端口 80，后者是 IIS 的默认值。
    * 如果你不能连接到远程主机使用的主机名 （在后续步骤中） 的 Visual Studio 中，测试代替主机名称的 IP 地址。

    > [!NOTE]
    > 如果你发布到 Azure VM 上运行的 IIS，必须将网络安全组中打开 Web 部署和 IIS 端口。 有关详细信息，请参阅[安装和运行的 IIS](/azure/virtual-machines/windows/quick-create-portal#open-port-80-for-web-traffic)。

1. 将此文件复制到其中运行 Visual Studio 的计算机。

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>导入 Visual Studio 中的发布设置和部署

1. 在计算机上必须在 Visual Studio 中打开 ASP.NET 项目，右键单击解决方案资源管理器中的项目并选择**发布**。

1. 如果你之前配置任何发布的配置文件，**发布**窗格中显示。 单击**创建新的配置文件**。

1. 在**选取发布目标**对话框中，单击**导入配置文件**。

    ![选择发布](../deployment/media/tutorial-publish-tool-import-profile.png)

1. 导航到你在上一节中创建的发布设置文件的位置。

1. 在**导入发布设置文件**对话框中，导航到并选择你在上一节中创建的配置文件，然后单击**打开**。

    Visual Studio 开始部署过程中，并且输出窗口会显示进度和结果。

    如果你遇到的任何部署错误，请单击**设置**以编辑设置。 修改设置，然后单击**验证**若要测试新的设置。

    ![在发布工具中编辑设置](../deployment/media/tutorial-configure-publish-settings-in-tool.png)

## <a name="next-steps"></a>后续步骤

在本教程中，创建发布设置文件、 导入 Visual Studio 和 ASP.NET 应用程序部署到 IIS。

> [!div class="nextstepaction"]
> [初探部署](../deployment/deploying-applications-services-and-components.md)
