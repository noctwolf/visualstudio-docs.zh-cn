---
title: 通过导入发布设置来发布到 IIS
description: 创建并导入发布配置文件，以便将应用程序从 Visual Studio 部署到 IIS
ms.date: 05/07/2018
ms.topic: tutorial
helpviewer_keywords:
- deployment, publish settings
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 13a4210e24fe64db79be897bc159477e9b2f5a3a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53897375"
---
# <a name="publish-an-application-to-iis-by-importing-publish-settings-in-visual-studio"></a>通过在 Visual Studio 中导入发布设置将应用程序发布到 IIS

可使用“发布”工具导入发布设置，然后部署应用。 在本文中，我们使用 IIS 的发布设置，但你可以使用类似的步骤导入 [Azure 应用服务](../deployment/tutorial-import-publish-settings-azure.md)的发布设置。 在某些情况下，对于每个 Visual Studio 安装，使用发布设置配置文件比为 IIS 手动配置部署要快。

这些步骤适用于 Visual Studio 中的 ASP.NET、ASP.NET Core 和 .NET Core 应用。 这些步骤对应于 Visual Studio 2017 版本 15.6。

在本教程中，你将：

> [!div class="checklist"]
> * 配置 IIS 以生成发布设置文件
> * 创建发布设置文件
> * 将发布设置文件导入 Visual Studio
> * 将应用部署到 IIS

发布设置文件 (\*.publishsettings) 与在 Visual Studio 中创建的发布配置文件 (\*.pubxml) 不同。 发布设置文件由 IIS 或 Azure 应用服务创建，或者可手动创建，然后可将其导入 Visual Studio。

> [!NOTE]
> 若只需要将 Visual Studio 发布配置文件（\*.pubxml 文件）从一个 Visual Studio 安装复制到另一个，则对于托管项目类型可以在 \\<projectname\>\Properties\PublishProfiles 文件夹中查找发布配置文件 \<profilename\>.pubxml。 对于网站则在 \App_Data 文件夹下进行查找。 发布配置文件是 MSBuild XML 文件。

## <a name="prerequisites"></a>系统必备

* 须安装 Visual Studio 2017 且具有 ASP.NET 和 .NET Framework 开发工作负载。 对于 .NET Core 应用，还需要 .NET Core 工作负载。

    如果尚未安装 Visual Studio，请转到  [Visual Studio 下载](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 页免费安装。

* 若要从 IIS 生成发布设置文件，必须具有运行 Windows Server 2012 或 Windows Server 2016 的计算机，并且必须正确配置 IIS Web 服务器角色。 还必须安装 ASP.NET 4.5 或 ASP.NET Core。 对于 ASP.NET Core，请参阅[发布到 IIS](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration)。 对于 ASP.NET 4.5，请参阅[使用 ASP.NET 3.5 和 ASP.NET 4.5 的 IIS 8.0](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)。

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>在 Visual Studio 中新建 ASP.NET 项目

1. 在运行 Visual Studio 的计算机中，依次选择“文件” > “新建项目”。

1. 在 Visual C# 或 Visual Basic 下选择“Web”，然后在中间窗格中选择“ASP.NET Web 应用程序(.NET Framework)”或（仅限 C#）“ASP.NET Core Web 应用程序”，然后单击“确定”。

    如果没有看到指定的项目模板，请单击“新建项目”对话框左侧窗格中的“打开 Visual Studio 安装程序”链接。 Visual Studio 安装程序启动。 请参阅本文中的先决条件，以确定必须安装的必需 Visual Studio 工作负载。

1. 选择“MVC”(.NET Framework) 或“Web 应用程序(模型-视图-控制器)”（适用于 .NET Core），并确保已选中“无身份验证”，然后单击“确定”。

1. 键入名称（例如“MyWebApp”），然后单击“确定”。

    Visual Studio 随即创建项目。

1. 选择“生成” > “生成解决方案”以生成项目。

## <a name="install-and-configure-web-deploy-on-windows-server"></a>在 Windows Server 上安装和配置 Web 部署

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

## <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>在 Windows Server 上的 IIS 中创建发布设置文件

[!INCLUDE [create-publish-settings-iis](../deployment/includes/create-publish-settings-iis.md)]

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>在 Visual Studio 中导入发布设置并进行部署

[!INCLUDE [import-publish-settings](../deployment/includes/import-publish-settings-vs.md)]

应用成功部署后，它应自动启动。 若在 Visual Studio 中无法启动该应用，请在 IIS 中启动。 对于 ASP.NET Core，需要确保将 DefaultAppPool 的应用程序池字段设置为“无托管代码”。

## <a name="next-steps"></a>后续步骤

在本教程中，创建了发布设置文件，将其导入 Visual Studio，并将 ASP.NET 应用部署到 IIS。 建议了解 Visual Studio 中其他发布选项的概述。

> [!div class="nextstepaction"]
> [初探部署](../deployment/deploying-applications-services-and-components.md)
