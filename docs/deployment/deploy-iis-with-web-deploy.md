---
title: 将 ASP.NET 部署到 IIS 使用 Web 部署
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
ms.openlocfilehash: a63d9947f544ddff1de81aaf34ed62c9646fba3d
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34794186"
---
# <a name="deploy-aspnet-to-a-remote-iis-computer-using-web-deploy-in-visual-studio"></a>将 ASP.NET 部署到远程 IIS 计算机使用 Visual Studio 中的 Web 部署

此文章介绍了如何设置和配置 Visual Studio 2017 ASP.NET MVC 4.5.2 应用程序并将其部署到 IIS。 本文包括基本的 Windows server 上的 IIS 配置设置和部署 Visual Studio 中的应用的步骤。 这些步骤是包含在内，以确保服务器具有必需组件安装，并您已准备好部署。 如果要部署 ASP.NET Core 应用程序，某些步骤将会不同。 部署 ASP.NET Core 应用程序，请参阅[发布到 IIS 应用程序通过导入发布设置](../deployment/tutorial-import-publish-settings-iis.md)有关的说明。 在 ASP.NET 和 ASP.NET Core 某些情况下，它是更快地部署到 IIS 通过导入发布设置。

这些过程已经过测试在这些服务器配置：
* Windows Server 2012 R2 和 IIS 8 （对于 Windows Server 2008 R2 中，服务器步骤会有所不同，）

## <a name="create-the-aspnet-452-application-on-the-visual-studio-computer"></a>创建 ASP.NET 4.5.2 Visual Studio 计算机上应用程序
  
1. 在计算机上运行 Visual Studio，选择**文件 > 新建项目**。

1. 下**Visual C#** 或**Visual Basic**，选择**Web**，然后在中间窗格中选择**ASP.NET Web 应用程序 (.NET Framework)**，然后单击**确定**。

    如果看不到指定的项目模板，请单击**打开 Visual Studio 安装程序**中的左窗格中的链接，**新项目**对话框。 Visual Studio 安装程序启动。 请参阅这篇文章，以标识所需的 Visual Studio 工作负荷，必须安装中的先决条件。

1. 选择**MVC** (.NET Framework) 并确保**无身份验证**已选择，然后单击**确定**。

1. 键入的名称，例如**MyWebApp**单击**确定**。

    Visual Studio 随即创建项目。

1. 选择**生成 > 生成解决方案**以生成项目。

## <a name="bkmk_configureIIS"></a> 安装和 Windows Server 上配置 IIS

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>更新 Windows Server 上的浏览器安全设置

如果在 Internet 资源管理器 （默认情况下已启用） 启用了增强的安全配置，你可能需要将某些域添加为受信任的站点，以使您能够下载某些 web 服务器组件。 通过转到添加受信任的站点**Internet 选项 > 安全 > 受信任的站点 > 站点**。 添加以下域。

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- iis.net

当你下载的软件时，可能会收到请求授予加载各种 web 站点脚本和资源的权限。 其中的某些资源不是必需的但若要简化此过程中，单击**添加**出现提示时。

## <a name="BKMK_deploy_asp_net"></a> 在 Windows Server 上安装 ASP.NET 4.5

如果你想要在 IIS 上安装 ASP.NET 的更多详细的信息，请参阅[IIS 8.0 使用 ASP.NET 3.5 和 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)。

1. 在左窗格中的服务器管理器中，选择**IIS**。 右键单击服务器并选择**Internet Information Services (IIS) Manager**。

1. 使用 Web 平台安装程序 (WebPI) 安装 ASP.NET 4.5 (从 Windows Server 2012 R2 中的服务器节点中，选择**获取新的 Web 平台组件**然后搜索 ASP.NET)

    ![RemoteDBG_IIS_AspNet_45](../debugger/media/remotedbg_iis_aspnet_45.png "RemoteDBG_IIS_AspNet_45")

    > [!NOTE]
    > 如果你使用的 Windows Server 2008 R2，安装 ASP.NET 4 而不使用此命令：

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -ir**

2. 重新启动系统 (或执行**net 停止已 /y**跟**net 启动 w3svc**从命令提示符以拾取到系统路径的更改)。

## <a name="BKMK_install_webdeploy"></a> 安装 Web 部署 Windows Server 上的 3.6

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

## <a name="BKMK_deploy_asp_net"></a> 在 Windows Server 计算机上配置 ASP.NET 网站

1. 打开 Windows 资源管理器并创建一个新的文件夹， **C:\Publish**，稍后将部署 ASP.NET 项目。

2. 如果尚未打开，请将它打开**Internet Information Services (IIS) Manager**。 (在服务器管理器的左窗格中，选择**IIS**。 右键单击服务器并选择**Internet Information Services (IIS) Manager**。)

3. 下**连接**在左窗格中，转到**站点**。

4. 选择**Default Web Site**，选择**基本设置**，并设置**物理路径**到**C:\Publish**。

5. 右键单击“默认网站”  节点，然后选择“添加应用程序” 。

6. 设置**别名**字段**MyASPApp**，接受默认应用程序池 (**DefaultAppPool**)，并设置**物理路径**到**C:\Publish**。

7. 下**连接**，选择**应用程序池**。 打开**DefaultAppPool**和将应用程序池字段设置为**ASP.NET v4.0** （ASP.NET 4.5 不是应用程序池的一个选项）。

8. 选择在 IIS 管理器站点后，选择**编辑权限**，并确保该 IUSR、 IIS_IUSRS 或配置应用程序池为授权的用户使用读取和执行权限的用户。 如果任何这些用户是否存在，将 IUSR 添加为具有读取和执行权限的用户。

## <a name="bkmk_webdeploy"></a> 发布和使用 Web 部署从 Visual Studio 部署应用

[!INCLUDE [deploy-app-web-deploy](../deployment/includes/deploy-app-web-deploy.md)]

此外，你可能需要阅读部分上[疑难解答端口](#bkmk_openports)。

## <a name="bkmk_openports"></a> 疑难解答： 打开 Windows Server 上的所需的端口

在大多数系统中，打开 ASP.NET 和 Web 部署安装所需的端口。 但是，你可能需要验证的端口打开。

> [!NOTE]
> 在 Azure VM，则必须打开端口通过[网络安全组](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80)。 

所需的端口：

* 80-所需的 IIS
* 8172-所需的 Web 部署来部署 Visual Studio 中的应用

1. 若要打开 Windows 服务器上的端口，请打开**启动**菜单中，搜索**高级安全 Windows 防火墙**。

2. 然后选择**入站规则 > 新规则 > 端口**。 选择**下一步**并在列表视图**特定本地端口**，输入端口号，单击**下一步**，然后**允许连接**，单击下一步，和将名称添加 (**IIS**， **Web 部署**，或**msvsmon**) 为入站规则。

    如果你想配置 Windows 防火墙的详细信息，请参阅[配置 Windows 防火墙以进行远程调试](../debugger/configure-the-windows-firewall-for-remote-debugging.md)。

3. 创建对其他所需端口的其他规则。

## <a name="next-steps"></a>后续步骤

在本教程中，创建发布设置文件、 导入 Visual Studio 和 ASP.NET 应用程序部署到 IIS。 您还可以部署通过导入发布设置。

> [!div class="nextstepaction"]
> [将部署到 IIS 通过导入发布设置](../deployment/tutorial-import-publish-settings-iis.md)