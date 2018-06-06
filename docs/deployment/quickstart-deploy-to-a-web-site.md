---
title: 将发布到网站的 Visual Studio |Microsoft 文档
ms.custom: ''
ms.date: 11/22/2017
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
ms.assetid: fc82b1f1-d342-4b82-9a44-590479f0a895
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0f722dcc4ada5643f9de3342b85469fa667d4b7c
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766547"
---
# <a name="publish-a-web-app-or-a-net-core-app-to-a-web-site-using-the-visual-studio-publish-tool"></a>将 web 应用或.NET Core 应用发布到网站使用 Visual Studio 发布工具

你可以使用**发布**工具，用于将 ASP.NET 应用程序发布到网站。

这些步骤适用于 ASP.NET、 ASP.NET Core、.NET 核心和 Visual Studio 中的 Python 应用。 For Node.js，支持步骤，但用户界面，则不同。

## <a name="prerequisites"></a>系统必备

* 你必须安装的 Visual Studio 2017 和**ASP.NET 和 web 开发**工作负荷和。**NET 桌面开发**工作负荷。 对于.NET Core 应用，你需要。**NET 核心**工作负荷。

    如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)页免费安装。

## <a name="create-a-new-project"></a>创建新项目 

1. 在 Visual Studio 中，依次选择“文件”>“新建项目”。

1. 下**Visual C#** 或**Visual Basic**，选择**Web**，然后在中间窗格中选择**ASP.NET Web 应用程序 (.NET Framework)** 或 (仅限 C#) **ASP.NET 核心 Web 应用程序**，然后单击**确定**。

1. 选择**MVC** (或选择**Web 应用程序 （模型-视图-控制器）** 为.NET Core)，请确保**无身份验证**已选择，然后单击**确定**.

1. 键入的名称，例如**MyWebApp**单击**确定**。

    Visual Studio 随即创建项目。

1. 选择**生成 > 生成解决方案**以生成项目。

## <a name="publish-to-a-web-site"></a>将发布到网站

1. 在解决方案资源管理器中，右键单击项目，选择“发布”。

    ![选择发布](../deployment/media/quickstart-publish-aspnet.png "选择发布")

1. 如果你之前配置任何发布的配置文件，**发布**窗格中显示。 单击**创建新的配置文件**。

1. 在**选取发布目标**对话框框中，选择**IIS，FTP，等**。

    ![选择 IIS、 FTP 等](../deployment/media/quickstart-publish-iis-ftp.png "选择 IIS、 FTP，等等。")

1. 单击“发布” 。

    配置文件将发布的设置对话框随即打开。

    ![选择文件夹](../deployment/media/quickstart-publish-settings-web.png "选择文件夹")

1. 在**发布方法**字段中，选择一种方法，例如**Web 部署**或**FTP**。

    接下来，你看到的设置对应于您发布方法。 Web 部署简化了 Web 应用程序和网站部署到 IIS 服务器，并且必须为应用程序服务器上安装。 使用[Web 平台安装程序](https://www.microsoft.com/web/downloads/platform.aspx)来进行安装。

1. 配置发布方法所需的设置，然后单击**验证连接**。

    如果服务器或目标可用以及你的设置正确，你将看到一条消息，指示连接将验证，并且你已准备好发布。

    ![验证你的连接](../deployment/media/quickstart-publish-web-deploy.png "验证你的连接")

1. 如果你想要配置其他部署设置，请单击**设置**。

    你可以配置选项，例如是否以部署 Debug 或 Release 配置，然后单击**保存**。 如果进行远程调试，则需要调试配置。

1. 若要发布，请单击**发布**。

    输出窗口显示部署进度和结果。

## <a name="next-steps"></a>后续步骤

在本快速入门教程，你学习了如何使用 Visual Studio 创建的发布配置文件。 你还可以配置发布配置文件通过导入发布设置。

> [!div class="nextstepaction"]
> [导入发布设置并部署到 IIS](tutorial-import-publish-settings-iis.md)
