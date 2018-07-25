---
title: 将发布到 Linux 应用服务
ms.custom: ''
ms.date: 07/23/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- azure
ms.openlocfilehash: e0268c2e65cd08274c2267ad2a4969f6015cbaf4
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "39234824"
---
# <a name="publish-an-aspnet-core-app-to-app-service-on-linux-using-visual-studio"></a>将 ASP.NET Core 应用发布到使用 Visual Studio 在 Linux 上的应用服务

可以使用**发布**工具，用于将 ASP.NET Core 应用发布到 Linux 上的 Azure 应用服务。

[!INCLUDE [quickstart-prereqs-azure-linux](includes/quickstart-prereqs-azure-linux.md)]

## <a name="publish-to-app-service-on-linux"></a>将发布到 Linux 应用服务

1. 在解决方案资源管理器，右键单击该项目并选择**发布**(或使用**构建** > **发布**菜单项)。

    ![在解决方案资源管理器的项目上下文菜单上的 Publish 命令](../deployment/media/quickstart-publish.png "选择发布")

1. 如果你以前配置了任何发布配置文件，**发布**窗格中的案例，请选择显示**创建新的配置文件**。

1. 在中**选取发布目标**对话框框中，选择**应用服务 Linux**。

    ![选择 Azure 应用服务](../deployment/media/quickstart-publish-linux.png "选择 Azure 应用服务")

1. 选择“发布”。 **创建应用服务**对话框随即出现。 使用你 Azure 帐户登录，如果有必要，则默认应用服务设置填充字段。

    ![创建应用服务](../deployment/media/quickstart-publish-settings-app-service-linux.png "创建 Azure 应用服务")

1. 选择“创建”。 Visual Studio 将应用部署到 Azure 应用服务，并在浏览器中加载 web 应用。 项目属性**发布**窗格显示了站点 URL 和其他详细信息。

    ![发布属性窗格中显示一个配置文件摘要](../deployment/media/quickstart-publish-app-service-summary.png)

## <a name="next-steps"></a>后续步骤

在此快速入门中，您学习了如何使用 Visual Studio 在 Linux 上创建部署到应用服务的发布配置文件。 您可以发布到 Linux 使用 Azure 的详细信息。

> [!div class="nextstepaction"]
> [Linux 应用服务](/azure/app-service/containers/app-service-linux-intro)
