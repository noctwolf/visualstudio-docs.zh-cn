---
title: 部署功能简介
description: 了解如何部署应用程序从 Visual Studio 的选项。
ms.custom: mvc
ms.date: 06/22/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- .NET applications, deploying
- components [Visual Studio], deploying
- installers
- publishing
- deploying applications [Visual Studio]
- deploying applications [Visual Studio], about deploying applications
- components [.NET Framework], deploying
ms.assetid: 63fcdd5b-2e54-4210-9038-65bc23167725
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 91dc83a1599058e1357c3ac7869f4284a1fc7fc5
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279110"
---
# <a name="quickstart-first-look-at-deployment-in-visual-studio"></a>快速入门： 首先看一下 Visual Studio 中的部署

通过部署应用程序、 服务或组件，您将其分发以便安装在其他计算机、 设备或服务器，或在云中。 你需要在 Visual Studio 中为所需的部署类型选择适当的方法。 （许多应用程序类型支持此处未介绍其他部署工具，如命令行部署或 NuGet。）

请参阅快速入门和教程，了解分步部署说明。 有关部署选项的概述，请参阅[哪些发布选项是最适合我？](deploying-applications-services-and-components-resources.md#what-publishing-options-are-right-for-me)。

## <a name="deploy-to-local-folder"></a>将部署到本地文件夹

部署到本地文件夹通常用于测试，或若要开始另一种工具用于最终部署的过渡的部署。

- **ASP.NET**， **ASP.NET Core**， **Node.js**， **Python**，和。**NET 核心**： 使用发布工具将部署到本地文件夹。 可用的具体选项取决于你的应用程序类型。 在解决方案资源管理器，右键单击项目并选择**发布**。 (如果以前已配置任何发布配置文件，必须单击**创建新的配置文件**。)接下来，选择**文件夹**。 有关详细信息，请参阅[部署到本地文件夹](quickstart-deploy-to-local-folder.md)。

    ![选择发布](../deployment/media/quickstart-publish.png)

- **Visual c + + 运行时**： 可以部署 Visual c + + 运行时使用本地部署或静态链接。 有关详细信息，请参阅[部署本机桌面应用程序 （Visual c + +）](/cpp/ide/deploying-native-desktop-applications-visual-cpp)。 

## <a name="publish-to-azure"></a>发布到 Azure

- **ASP.NET**， **ASP.NET Core**， **Python**，和**Node.js**： 你可以使用发布工具快速将应用部署到 Azure App Service 或 Azure 虚拟机。 在解决方案资源管理器中，右键单击项目，选择“发布”。 (如果以前已配置任何发布配置文件，必须单击**创建新的配置文件**。)在发布对话框中，选择任一**应用服务**或**Azure 虚拟机**，然后按照配置步骤进行操作。

    ![选择 Azure 应用服务](../deployment/media/quickstart-publish-azure.png "选择 Azure 应用服务")

    在 Visual Studio 2017 版本 15.7 及更高版本中，你可以部署到 ASP.NET Core 应用**适用于 Linux 应用服务**。

    对于 Python 应用程序，另请参阅[Python-发布到 Azure App Service](/visualstudio/python/publishing-python-web-applications-to-azure-from-visual-studio?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)。

    有关快速介绍，请参阅[发布到 Azure](quickstart-deploy-to-azure.md)并[发布到 Linux](quickstart-deploy-to-linux.md)。 另请参阅[向 Azure 发布 ASP.NET Core 应用](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)。 有关使用 Git 进行部署，请参阅[连续部署到使用 Git 的 Azure ASP.NET Core](/aspnet/core/publishing/azure-continuous-deployment)。

    有关从 Azure 应用服务的发布配置文件导入到 Visual Studio 的信息，请参阅[导入发布设置和部署到 Azure](../deployment/tutorial-import-publish-settings-azure.md)。

    > [!NOTE]
    > 如果你还没有 Azure 帐户，则可以[此处注册](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio)。

## <a name="publish-to-web-or-deploy-to-network-share"></a>发布到 Web 或部署到网络共享

- **ASP.NET**， **ASP.NET Core**， **Node.js**，和**Python**： 你可以使用发布工具将部署到对使用 FTP 或 Web 部署网站。 有关详细信息，请参阅[部署到网站](quickstart-deploy-to-a-web-site.md)。

    在解决方案资源管理器中，右键单击项目，选择“发布”。 (如果以前已配置任何发布配置文件，必须单击**创建新的配置文件**。)在发布工具中，选择你想，并执行配置步骤的选项。

    ![选择 IIS、 FTP 等。](../deployment/media/quickstart-publish-iis-ftp.png)

    有关导入发布配置文件在 Visual Studio 中的信息，请参阅[导入发布设置和部署到 IIS](../deployment/tutorial-import-publish-settings-iis.md)。

    您还可以部署 ASP.NET 应用程序和服务中的其他方法的数量。 有关详细信息，请参阅[部署 ASP.NET web 应用程序和服务](http://www.asp.net/aspnet/overview/deployment)。

- **Visual c + + 运行时**： 可以部署使用集中部署 Visual c + + 运行时。 有关详细信息，请参阅[部署本机桌面应用程序 （Visual c + +）](/cpp/ide/deploying-native-desktop-applications-visual-cpp)。 

- **Windows 桌面**可以发布到 web 服务器或网络文件共享使用 ClickOnce 部署的 Windows 桌面应用程序。 用户随后只需一次单击即可安装应用程序。 有关详细信息，请参阅[部署桌面应用使用 ClickOnce](how-to-publish-a-clickonce-application-using-the-publish-wizard.md)并[将本机应用使用 ClickOnce 部署](/cpp/ide/clickonce-deployment-for-visual-cpp-applications)。

## <a name="publish-to-microsoft-store"></a>将发布到 Microsoft Store

从 Visual Studio 中，可以创建应用包以部署到 Microsoft Store。

- **UWP**： 可以将应用打包和部署使用菜单项。 有关详细信息，请参阅[通过使用 Visual Studio 打包 UWP 应用](/windows/uwp/packaging/packaging-uwp-apps)。

    ![创建应用程序包](../deployment/media/feature-tour-create-app-package.jpg)

- **Windows 桌面**： 可以将它们部署到 Visual Studio 2017 版本 15.4 中开始使用桌面桥将 Microsoft Store。 若要执行此操作，首先创建一个 Windows 应用程序打包项目。 有关详细信息，请参阅[为 （桌面桥） 的 Microsoft Store 打包桌面应用](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)。

    ![桌面桥](../deployment/media/feature-tour-desktop-bridge.png)

## <a name="deploy-to-a-device-uwp"></a>将部署到设备 (UWP)

如果要部署用于测试的设备上的 UWP 应用，请参阅[Visual Studio 中在远程计算机上的运行 UWP 应用](../debugger/run-windows-store-apps-on-a-remote-machine.md)。

## <a name="create-an-installer-package-windows-client"></a>创建安装程序包 （Windows 客户端）

如果需要更复杂的安装的桌面应用程序比[ClickOnce](how-to-publish-a-clickonce-application-using-the-publish-wizard.md)可以提供，你可以创建的安装程序包、 安装项目或自定义引导程序。

- 可以使用创建的基于 MSI 的 WiX 安装程序[WiX 工具集 Visual Studio 2017 扩展](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension)。

- [InstallShield](https://www.flexerasoftware.com/producer/products/software-installation/installshield-software-installer/tab/requirements)从 Flexera 软件可与结合使用 Visual Studio 2017 （社区版不支持）。 请注意，InstallShield Limited Edition 不再包含在 Visual Studio 中，不支持在 Visual Studio 2017;请咨询[Flexera 软件](http://learn.flexerasoftware.com/content/IS-EVAL-InstallShield-Limited-Edition-Visual-Studio)有关未来的可用性。

- 如果你想要创建安装项目 (vdproj)，安装[Visual Studio 2017 安装程序项目扩展](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.MicrosoftVisualStudio2017InstallerProjects#overview)。

- 可以通过配置名为引导程序的一般安装程序安装桌面应用程序的必备组件。 有关详细信息，请参阅[应用程序部署必备](../deployment/application-deployment-prerequisites.md)。

## <a name="deploy-to-test-lab"></a>部署到测试实验室

您可以实现更复杂的开发和测试通过部署到虚拟环境的应用程序。 有关详细信息，请参阅[在实验室环境测试](../test/lab-management/using-a-lab-environment-for-your-application-lifecycle.md)。

## <a name="devops-deployment"></a>DevOps 部署

在团队环境中，可以使用 Azure 管道以启用对应用程序的持续部署。 有关详细信息，请参阅[Azure 管道](/azure/devops/pipelines/index)并[部署到 Azure](/azure/devops/deploy-azure/index)。

## <a name="deployment-for-other-app-types"></a>对于其他应用类型的部署

| 应用类型 | 部署方案 | 链接 |
| --- | --- | --- |
| **Office 应用程序** | 可以从 Visual Studio 的 Office 发布外接程序。 | [部署和发布 Office 外接程序](https://dev.office.com/docs/add-ins/publish/publish) |
| **WCF 或 OData 服务**  | 其他应用程序可以使用 WCF RIA 服务部署到 web 服务器。 | [开发和部署 WCF 数据服务](/dotnet/framework/data/wcf/developing-and-deploying-wcf-data-services) |
| **LightSwitch** | LightSwitch 在 Visual Studio 2017 中，不再受支持，但仍然可以从 Visual Studio 2015 及更早版本部署。 | [部署 LightSwitch 应用程序](https://msdn.microsoft.com/Library/4818d933-295c-4ecc-9148-7ad9ca28dcdb) | 

## <a name="next-steps"></a>后续步骤

在本教程中，您需要快速看一下不同的应用程序的部署选项。

> [!div class="nextstepaction"]
> [哪些发布选项是最适合我？](deploying-applications-services-and-components-resources.md#what-publishing-options-are-right-for-me)
