---
title: 将 ASP.NET 部署到 IIS，使用 Web 部署
ms.custom: ''
ms.date: 06/04/2018
ms.technology: vs-ide-deployment
ms.topic: tutorial
ms.assetid: 9cb339b5-3caf-4755-aad1-4a5da54b2a23
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 4705ca6e72001f8930e2fa4270515df53e1213a8
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2018
ms.locfileid: "39080845"
---
# <a name="deploy-aspnet-to-a-remote-iis-computer-using-web-deploy-in-visual-studio"></a>将 ASP.NET 部署到远程 IIS 计算机，在 Visual Studio 中使用 Web 部署

此文章介绍了如何设置和配置 Visual Studio 2017 ASP.NET MVC 4.5.2 应用程序并将其部署到 IIS。 本文包含有关 Windows server 上的 IIS 的基本配置设置和部署该应用程序从 Visual Studio 的步骤。 这些步骤是包括在内，以确保服务器已要求安装组件，已准备好部署。 如果要部署的 ASP.NET Core 应用程序，某些步骤会有所不同。 若要部署 ASP.NET Core 应用，请参阅[发布到 IIS 的应用程序，通过导入发布设置](../deployment/tutorial-import-publish-settings-iis.md)有关的说明。 在 ASP.NET 和 ASP.NET Core 某些情况下，它是更快地将部署到 IIS 通过导入发布设置。

这些服务器配置上进行了测试这些过程：
* Windows Server 2012 R2 和 IIS 8 （对于 Windows Server 2008 R2 中，服务器，步骤会有所不同）

## <a name="create-the-aspnet-452-application-on-the-visual-studio-computer"></a>创建 ASP.NET 4.5.2 在 Visual Studio 计算机上应用程序
  
1. 在计算机上运行 Visual Studio，选择**文件** > **新项目**。

1. 下**Visual C#** 或**Visual Basic**，选择**Web**，然后在中间窗格中选择任一**ASP.NET Web 应用程序 (.NET Framework)**，然后单击**确定**。

    如果看不到指定的项目模板，请单击**打开 Visual Studio 安装程序**的左窗格中的链接**新项目**对话框。 Visual Studio 安装程序启动。 请参阅这篇文章，以标识所需的 Visual Studio 工作负荷，必须安装中的先决条件。

1. 选择**MVC** (.NET Framework)，请确保**无身份验证**已选择，然后单击**确定**。

1. 键入一个名称，如**MyWebApp**然后单击**确定**。

    Visual Studio 随即创建项目。

1. 选择**构建** > **生成解决方案**以生成项目。

## <a name="install-and-configure-iis-on-windows-server"></a>安装和 Windows Server 上配置 IIS

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>更新 Windows Server 上的浏览器安全设置

如果在 Internet Explorer （默认情况下已启用） 中启用了增强的安全配置，您可能需要将某些域添加为受信任的站点，以便可以下载某些 web 服务器组件。 添加可信的站点，通过转到**Internet 选项** > **安全** > **受信任的站点** > **站点**. 添加以下域。

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- iis.net

下载软件时，可能会显示请求授予权限以加载各种 web 站点脚本和资源。 以下一些资源不是必需的但若要简化此过程中，单击**添加**出现提示时。

## <a name="install-aspnet-45-on-windows-server"></a>Windows Server 上安装 ASP.NET 4.5

如果你想要在 IIS 上安装 ASP.NET 的更多详细的信息，请参阅[使用 ASP.NET 3.5 和 ASP.NET 4.5 的 IIS 8.0](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)。

1. 在服务器管理器的左窗格中，选择**IIS**。 右键单击服务器，然后选择**Internet 信息服务 (IIS) 管理器**。

1. 使用 Web 平台安装程序 (WebPI) 安装 ASP.NET 4.5 (从 Windows Server 2012 R2 中的服务器节点，选择**获取新的 Web 平台组件**，然后搜索 ASP.NET)

    ![RemoteDBG_IIS_AspNet_45](../debugger/media/remotedbg_iis_aspnet_45.png "RemoteDBG_IIS_AspNet_45")

    > [!NOTE]
    > 如果使用 Windows Server 2008 R2，安装 ASP.NET 4 改为使用此命令：

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -ir**

2. 重新启动系统 (或执行**net stop was /y 和**跟**net start w3svc**在命令提示符下，若要应用到系统路径的更改)。

## <a name="install-web-deploy-36-on-windows-server"></a>安装 Web 部署 Windows Server 上的 3.6

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

## <a name="configure-aspnet-web-site-on-the-windows-server-computer"></a>Windows Server 计算机上配置 ASP.NET 网站

1. 打开 Windows 资源管理器，并创建一个新文件夹**C:\Publish**、 更高版本将部署的 ASP.NET 项目。

2. 如果尚未打开，打开**Internet 信息服务 (IIS) 管理器**。 (在服务器管理器的左窗格中，选择**IIS**。 右键单击服务器，然后选择**Internet 信息服务 (IIS) 管理器**。)

3. 下**连接**在左窗格中，转到**站点**。

4. 选择**Default Web Site**，选择**基本设置**，并设置**物理路径**到**C:\Publish**。

5. 右键单击“默认网站”  节点，然后选择“添加应用程序” 。

6. 设置**别名**字段**MyASPApp**，接受默认应用程序池 (**DefaultAppPool**)，并设置**物理路径**到**C:\Publish**。

7. 下**连接**，选择**应用程序池**。 打开**DefaultAppPool**并将应用程序池字段设置为**ASP.NET v4.0** （ASP.NET 4.5 不是应用程序池的选项）。

8. 在 IIS 管理器中选择站点后，选择**编辑权限**，并确保该 IUSR、 IIS_IUSRS 或配置应用程序池为授权的用户使用读取和执行权限的用户。 如果没有任何这些用户不存在，将 IUSR 添加为具有读取和执行权限的用户。

## <a name="publish-and-deploy-the-app-using-web-deploy-from-visual-studio"></a>发布和部署使用从 Visual Studio Web 部署的应用

[!INCLUDE [deploy-app-web-deploy](../deployment/includes/deploy-app-web-deploy.md)]

此外，您可能需要阅读有关如何排查端口下面一节。

## <a name="troubleshoot-open-required-ports-on-windows-server"></a>故障排除： 打开 Windows Server 上的所需的端口

在大多数系统中，通过安装 ASP.NET 和 Web 部署打开所需的端口。 但是，您可能需要验证端口打开。

> [!NOTE]
> 在 Azure VM 上，则必须打开端口通过[网络安全组](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80)。 

所需的端口：

* 80-所需的 IIS
* 8172-所需的 Web 部署来部署该应用程序从 Visual Studio

1. 若要打开 Windows 服务器上的端口，请打开**启动**菜单中，搜索**高级安全 Windows 防火墙**。

2. 然后选择**入站规则** > **新规则** > **端口**。 选择**下一步**并在**特定本地端口**，输入端口号，单击**下一步**，然后**允许连接**，单击下一步，和添加名称 (**IIS**， **Web Deploy**，或**msvsmon**) 的入站规则。

    如果您想配置 Windows 防火墙的详细信息，请参阅[配置 Windows 防火墙以允许远程调试](../debugger/configure-the-windows-firewall-for-remote-debugging.md)。

3. 创建其他规则中的其他所需的端口。

## <a name="next-steps"></a>后续步骤

在本教程中，创建发布设置文件、 导入到 Visual Studio 和 ASP.NET 应用部署到 IIS。 您还可以部署通过导入发布设置。

> [!div class="nextstepaction"]
> [将部署到 IIS 通过导入发布设置](../deployment/tutorial-import-publish-settings-iis.md)
