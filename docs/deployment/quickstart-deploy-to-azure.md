---
title: 发布到 Azure 应用服务
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
- azure
ms.openlocfilehash: 7761164182188366425a81518f3d0513361b6f19
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2018
ms.locfileid: "39077838"
---
# <a name="publish-a-web-app-to-azure-app-service-using-visual-studio"></a>将 Web 应用发布到 Azure 应用服务中使用 Visual Studio

可以使用**发布**工具，用于将 ASP.NET、 ASP.NET Core、 Node.js 和.NET Core 应用发布到 Azure 应用服务或 Azure App Service Linux （使用容器）。 对于 Python 应用程序，在执行的步骤[Python-发布到 Azure App Service](../python/publishing-python-web-applications-to-azure-from-visual-studio.md)。

[!INCLUDE [quickstart-prereqs-azure](includes/quickstart-prereqs-azure.md)]

## <a name="publish-to-azure-app-service"></a>发布到 Azure 应用服务

1. 在解决方案资源管理器，右键单击该项目并选择**发布**(或使用**构建** > **发布**菜单项)。

    ![在解决方案资源管理器的项目上下文菜单上的 Publish 命令](../deployment/media/quickstart-publish.png "选择发布")

1. 如果你以前配置了任何发布配置文件，**发布**窗格中的案例，请选择显示**创建新的配置文件**。

1. 在中**选取发布目标**对话框框中，选择**应用服务**。

    ![选择 Azure 应用服务](../deployment/media/quickstart-publish-azure.png "选择 Azure 应用服务")

1. 选择“发布”。 **创建应用服务**对话框随即出现。 使用你 Azure 帐户登录，如果有必要，则默认应用服务设置填充字段。

    ![创建应用服务](../deployment/media/quickstart-publish-settings-app-service.png "创建 Azure 应用服务")

1. 选择“创建”。 Visual Studio 将应用部署到 Azure 应用服务，并在浏览器中加载 web 应用。 项目属性**发布**窗格显示了站点 URL 和其他详细信息。

    ![发布属性窗格中显示一个配置文件摘要](../deployment/media/quickstart-publish-app-service-summary.png)

## <a name="next-steps"></a>后续步骤

在此快速入门中，您学习了如何使用 Visual Studio 创建发布配置文件部署到 Azure。 你还可以配置发布配置文件通过导入发布设置从 Azure 应用服务。

> [!div class="nextstepaction"]
> [导入发布设置并部署到 Azure](tutorial-import-publish-settings-azure.md)
