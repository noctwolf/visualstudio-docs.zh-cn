---
title: 部署功能教程
description: 了解有关将应用从 Visual Studio 部署选项。
ms.custom: mvc
ms.date: 11/26/2017
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
ms.openlocfilehash: 8d2c84b8e5d37876d890d40144b281e236fdcd0c
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766306"
---
# <a name="quickstart-first-look-at-deployment-in-visual-studio"></a>快速入门： 第一次查看 Visual Studio 中的部署

通过部署应用程序、服务或组件，你可以将其分发以便安装于其他计算机、设备、服务器或云中。 你需要在 Visual Studio 中为所需的部署类型选择适当的方法。 （许多应用程序类型支持此处未介绍其他部署工具，如命令行部署或 NuGet。）

请参阅有关分步部署说明的教程。 如果你正在部署 web 应用程序，并需要更深入的信息来确定最佳的部署选项，从 Visual Studio，请参阅[哪些发布选项是适合我？](../ide/not-in-toc/web-publish-options.md)。

## <a name="deploy-to-local-folder"></a>将部署到本地文件夹

部署到本地文件夹通常用于测试或开始另一种工具将使用最终部署的过渡的部署。

- **ASP.NET**， **ASP.NET Core**， **Node.js**， **Python**，和。*.NET Core**： 使用发布工具将部署到本地文件夹。 确切的可用选项取决于你的应用程序类型。 在解决方案资源管理器，右键单击你的项目并选择**发布**。 (如果你之前配置任何发布配置文件，必须单击**创建新的配置文件**。)接下来，选择**文件夹**。 有关详细信息，请参阅[部署到本地文件夹](quickstart-deploy-to-local-folder.md)。

    ![选择发布](../deployment/media/quickstart-publish.png)

- **Visual c + + 运行时**： 你可以部署 Visual c + + 运行库使用本地部署或静态链接。 有关详细信息，请参阅[部署本机桌面应用程序 （Visual c + +）](/cpp/ide/deploying-native-desktop-applications-visual-cpp)。 

## <a name="azure"></a> 将发布到 Azure

- **ASP.NET**， **ASP.NET Core**， **Python**，和**Node.js**： 你可以使用发布工具快速将应用部署到 Azure App Service 或 Azure 虚拟机。 在解决方案资源管理器中，右键单击项目，选择“发布”。 (如果你之前配置任何发布配置文件，必须单击**创建新的配置文件**。)在发布对话框中，选择**App Service**或**Azure 虚拟机**，然后按照配置步骤。

    ![选择 Azure App Service](../deployment/media/quickstart-publish-azure.png "选择 Azure App Service")

    在 Visual Studio 2017 15.7 版，你可以部署到 ASP.NET Core 应用**适用于 Linux 的 App Service**。

    有关从 Azure App Service 的发布配置文件导入到 Visual Studio 的信息，请参阅[导入发布设置和部署到 Azure](../deployment/tutorial-import-publish-settings-azure.md)。

    快速介绍，请参阅[发布到 Azure](quickstart-deploy-to-azure.md)。 另请参阅[向 Azure 发布 ASP.NET Core 应用](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)。 有关使用 Git 进行部署，请参阅[连续部署到使用 Git 的 Azure ASP.NET Core](/aspnet/core/publishing/azure-continuous-deployment)。

    > [!NOTE]
    > 如果你还没有 Azure 帐户，则可以[此处注册](https://azure.microsoft.com/free/?ref=microsoft.com&utm_source=microsoft.com&utm_medium=doc&utm_campaign=visualstudio)。

## <a name="web"></a> 发布到 Web 或部署到网络共享

- **ASP.NET**， **ASP.NET Core**， **Node.js**，和**Python**： 你可以使用发布工具将部署到对使用 FTP 或 Web 部署网站。 有关详细信息，请参阅[部署到网站](quickstart-deploy-to-a-web-site.md)。

    在解决方案资源管理器中，右键单击项目，选择“发布”。 (如果你之前配置任何发布配置文件，必须单击**创建新的配置文件**。)在发布工具中，选择你想，并执行的配置步骤的选项。

    ![选择 IIS、 FTP，等等。](../deployment/media/quickstart-publish-iis-ftp.png)

    有关导入 Visual Studio 中的发布配置文件的信息，请参阅[导入发布设置和部署到 IIS](../deployment/tutorial-import-publish-settings-iis.md)。

    你还可以部署 ASP.NET 应用程序和多种其他方式的服务。 有关详细信息，请参阅[部署 ASP.NET web 应用程序和服务](http://www.asp.net/aspnet/overview/deployment)。

- **Visual c + + 运行时**： 你可以部署 Visual c + + 运行库使用集中部署。 有关详细信息，请参阅[部署本机桌面应用程序 （Visual c + +）](/cpp/ide/deploying-native-desktop-applications-visual-cpp)。 

- **Windows 桌面**可以发布到 web 服务器或网络文件共享使用 ClickOnce 部署的 Windows 桌面应用程序。 用户随后只需一次单击即可安装应用程序。 有关详细信息，请参阅[部署桌面应用程序中使用 ClickOnce](how-to-publish-a-clickonce-application-using-the-publish-wizard.md)和[部署使用 ClickOnce 的本机应用](/cpp/ide/clickonce-deployment-for-visual-cpp-applications)。

## <a name="microsoft_store"></a> 将发布到 Microsoft 存储

从 Visual Studio 中，你可以创建适用于部署到 Microsoft 应用商店应用包。

- **UWP**： 可以打包你的应用程序和部署使用菜单项。 有关详细信息，请参阅[通过使用 Visual Studio 打包 UWP 应用](/windows/uwp/packaging/packaging-uwp-apps)。

    ![创建应用程序包](../deployment/media/feature-tour-create-app-package.jpg)

- **Windows 桌面**： 你可以将它们部署到 Microsoft 应用商店使用桌面桥在 Visual Studio 2017 版本 15.4 中启动。 若要执行此操作，首先创建一个 Windows 应用程序打包项目。 有关详细信息，请参阅[打包成 Microsoft 应用商店 （桌面桥） 桌面应用程序](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)。

    ![桌面桥](../deployment/media/feature-tour-desktop-bridge.png)

## <a name="deploy-to-a-device-uwp"></a>部署到设备 (UWP)

如果要部署用于测试的设备上的 UWP 应用，请参阅[Visual Studio 中在远程计算机上运行的 UWP 应用](../debugger/run-windows-store-apps-on-a-remote-machine.md)。

## <a name="installer"></a> 创建的安装程序包 （Windows 客户端）

如果需要更复杂的安装的桌面应用程序比[ClickOnce](how-to-publish-a-clickonce-application-using-the-publish-wizard.md)可以提供，你可以创建的安装程序包、 安装项目或自定义引导程序。

- 可以使用创建的基于 MSI 的 WiX 安装程序[WiX 工具集 Visual Studio 2017 扩展](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension)。

- [InstallShield](https://www.flexerasoftware.com/producer/products/software-installation/installshield-software-installer/tab/requirements)从 Flexera 软件可与使用 Visual Studio 2017 (Community Edition 不支持)。 请注意，InstallShield Limited Edition 不再包含在 Visual Studio 中，在 Visual Studio 2017; 不支持咨询[Flexera 软件](http://learn.flexerasoftware.com/content/IS-EVAL-InstallShield-Limited-Edition-Visual-Studio)有关将来的可用性。

- 如果你想要创建安装项目 (vdproj)，安装[Visual Studio 自 2017 年 1 安装程序项目扩展](https://marketplace.visualstudio.com/items?itemName=VisualStudioProductTeam.MicrosoftVisualStudio2017InstallerProjects#overview)。

- 你可以通过配置一般安装程序，这被称为引导程序安装桌面应用程序的必备组件。 有关详细信息，请参阅[应用程序部署必备](../deployment/application-deployment-prerequisites.md)。

## <a name="deploy-to-test-lab"></a>部署测试实验室

你可以启用更复杂的开发和测试部署到虚拟环境的应用程序。 有关详细信息，请参阅[实验室环境测试](../test/lab-management/using-a-lab-environment-for-your-application-lifecycle.md)。

## <a name="devops-deployment"></a>DevOps 部署

在团队环境中，可以使用 Visual Studio Team Services (VSTS) 以启用你的应用程序的连续部署。 有关详细信息，请参阅[生成和发布](/vsts/build-release/index)和[部署到 Azure](/vsts/deploy-azure/index)。

## <a name="deployment-for-other-app-types"></a>对于其他应用程序类型的部署

| 应用类型 | 部署方案 | 链接 |
| --- | --- | --- |
| **Office 应用程序** | 你可以从 Visual Studio 的 Office 发布外接程序。 | [部署和发布 Office 外接程序](https://dev.office.com/docs/add-ins/publish/publish) |
| **WCF 或 OData 服务**  | 其他应用程序可以使用你部署到 web 服务器的 WCF RIA 服务。 | [开发和部署 WCF 数据服务](/dotnet/framework/data/wcf/developing-and-deploying-wcf-data-services) |
| **LightSwitch** | LightSwitch 中 Visual Studio 2017，不再支持，但仍可以从 Visual Studio 2015 及更早版本部署。 | [部署 LightSwitch 应用程序](http://msdn.microsoft.com/Library/4818d933-295c-4ecc-9148-7ad9ca28dcdb) | 

## <a name="next-steps"></a>后续步骤

在本教程中，你需要时间快速了解一下不同的应用程序的部署选项。 如果要部署的 web 应用程序，例如 ASP.NET，请阅读更深入一些 Visual Studio 中提供的部署选项。

> [!div class="nextstepaction"]
> [哪些发布选项是否适合我？](../ide/not-in-toc/web-publish-options.md)

