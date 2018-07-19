---
title: 部署到本地文件夹
ms.custom: ''
ms.date: 06/22/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, local folder
ms.assetid: adb461c4-812a-4b8c-b2ab-96002379f6a9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 517698aa2e042d74138579dae3633930b338cd61
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2018
ms.locfileid: "38781908"
---
# <a name="deploy-an-app-to-a-local-folder-using-visual-studio"></a>将应用部署到使用 Visual Studio 的本地文件夹

可以使用**发布**工具，用于从 Visual Studio 将 ASP.NET、 ASP.NET Core、.NET Core 和 Python 应用发布到本地文件夹。 适用于 Node.js，支持步骤但用户界面不同。

[!INCLUDE [quickstart-prereqs](includes/quickstart-prereqs.md)]

## <a name="deploy-to-a-local-folder"></a>部署到本地文件夹

1. 在解决方案资源管理器，右键单击该项目并选择**发布**(或使用**构建** > **发布**菜单项)。

    ![在解决方案资源管理器的项目上下文菜单上的 Publish 命令](../deployment/media/quickstart-publish.png "选择发布")

1. 如果你以前配置了任何发布配置文件，**发布**窗格会显示。 选择**创建新的配置文件**。

1. 在中**选取发布目标**对话框框中，选择**文件夹**。

    ![选择发布某种目标的本地文件夹](../deployment/media/quickstart-publish-folder.png "选择文件夹")

1. 输入路径，或选择**浏览**若要指定本地文件夹。

1. 选择“发布”。 Visual Studio 生成项目，并将其发布到指定的文件夹。 项目属性**发布**窗格出现，显示一个配置文件摘要。

    ![发布属性窗格中显示一个配置文件摘要](../deployment/media/quickstart-publish-folder-summary.png)

1. 若要配置部署设置，请选择**配置**中的配置文件摘要，然后选择**设置**选项卡。

    ![配置文件的设置](../deployment/media/quickstart-profile-settings.png "配置文件的设置")

1. 配置选项，如是否以部署调试或发布配置，然后选择**保存**。

1. 若要重新发布，请选择**发布**。

可按照任何喜欢的方式部署已发布的文件。 例如，包中对其 *.zip*文件，使用一个简单的复制命令，或使用所选的任何安装包进行部署。

## <a name="next-steps"></a>后续步骤

- [使用发布工具部署 .NET Core 应用程序](/dotnet/core/deploying/deploy-with-vs?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- [为 Microsoft Store 打包桌面应用（桌面桥）](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net?toc=/visualstudio/deployment/toc.json&bc=/visualstudio/deployment/_breadcrumb/toc.json)
- (.NET)[部署.NET Framework 和应用程序](/dotnet/framework/deployment/)
