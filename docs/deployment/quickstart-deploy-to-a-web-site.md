---
title: 发布到网站
ms.custom: ''
ms.date: 06/22/2018
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
ms.openlocfilehash: 036d7549995f79808142c3a0a64e7e5f2075df2c
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2018
ms.locfileid: "39077498"
---
# <a name="publish-a-web-app-to-a-web-site-using-visual-studio"></a>将 Web 应用发布到网站上使用 Visual Studio

可以使用**发布**工具，用于从 Visual Studio 将 ASP.NET、 ASP.NET Core、.NET Core 和 Python 应用发布到网站。 适用于 Node.js，支持步骤但用户界面不同。

[!INCLUDE [quickstart-prereqs](includes/quickstart-prereqs.md)]

## <a name="publish-to-a-web-site"></a>将发布到网站

1. 在解决方案资源管理器，右键单击该项目并选择**发布**(或使用**构建** > **发布**菜单项)。

    ![在解决方案资源管理器的项目上下文菜单上的 Publish 命令](../deployment/media/quickstart-publish.png "选择发布")

1. 如果你以前配置了任何发布配置文件，**发布**窗格会显示。 选择**创建新的配置文件**。

1. 在中**选取发布目标**对话框框中，选择**IIS、 FTP 等**。

    ![选择 IIS、 FTP 等](../deployment/media/quickstart-publish-iis-ftp.png "选择 IIS、 FTP 等。")

1. 选择“发布”。 该配置文件的发布的设置对话框随即打开。

    ![选择文件夹](../deployment/media/quickstart-publish-settings-web.png "选择文件夹")

1. 在中**发布方法**字段中，选择一种方法，例如**Web Deploy**或**FTP**。 接下来，您看到的设置对应于发布方法。 Web 部署简化了 Web 应用程序和网站部署到 IIS 服务器，必须为应用程序服务器上安装。 使用[Web 平台安装程序](https://www.microsoft.com/web/downloads/platform.aspx)进行安装。

1. 配置发布方法所需的设置，并选择**验证连接**。 如果服务器或目标可用且你的设置是否正确，此消息，指明连接进行验证，并准备好发布。

    ![验证你的连接](../deployment/media/quickstart-publish-web-deploy.png "验证你的连接")

1. 选择**设置**若要配置其他部署设置，例如，是否要部署的调试或发布配置中，，然后选择**保存**。 如果进行远程调试，则需要调试配置。

1. 若要发布，请选择**发布**。 输出窗口显示部署进度和结果。

## <a name="next-steps"></a>后续步骤

在此快速入门中，您学习了如何使用 Visual Studio 创建发布配置文件。 你还可以配置发布配置文件通过导入发布设置。

> [!div class="nextstepaction"]
> [导入发布设置并部署到 IIS](tutorial-import-publish-settings-iis.md)
