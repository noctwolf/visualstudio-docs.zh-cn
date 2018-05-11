---
title: 将部署到本地文件夹的 Visual Studio |Microsoft 文档
ms.custom: ''
ms.date: 05/08/2018
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
ms.openlocfilehash: a3b54a8fa30ef5eafcc5ebce5c81cc7b80be6fb6
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
---
# <a name="deploy-a-web-app-or-net-core-app-to-a-local-folder-using-the-visual-studio-publish-tool"></a>将 web 应用或.NET Core 应用部署到使用 Visual Studio 发布工具的本地文件夹

你可以使用**发布**工具以将你的应用程序发布到本地文件夹。 

这些步骤适用于 ASP.NET、 ASP.NET Core、.NET 核心和 Visual Studio 中的 Python 应用。 For Node.js，支持步骤，但用户界面，则不同。

## <a name="prerequisites"></a>系统必备

* 你必须安装的 Visual Studio 2017 和 **.NET Framework**和 **.NET 核心**安装的开发工作负荷。

    如果尚未安装 Visual Studio，请在[此处](http://www.visualstudio.com)免费安装。

## <a name="create-a-new-project"></a>创建新项目 

1. 在 Visual Studio 中，依次选择“文件”>“新建项目”。

1. 下**Visual C#** 或**Visual Basic**，选择 **.NET 核心**，然后在中间窗格中选择**控制台应用程序 (.NET Core)**。

1. 键入的名称，例如**MyLocalApp**单击**确定**。

    Visual Studio 随即创建项目。

## <a name="deploy-to-a-local-folder"></a>将部署到本地文件夹

1. 在解决方案资源管理器中，右键单击项目，选择“发布”。

    ![选择发布](../deployment/media/quickstart-publish.png "选择发布")

1. 如果你之前配置任何发布的配置文件，**发布**窗格中显示。 单击**创建新的配置文件**。

1. 在**选取发布目标**对话框框中，选择**文件夹**。

    ![选择文件夹](../deployment/media/quickstart-publish-folder.png "选择文件夹")

1. 输入的路径或单击**浏览**以浏览到本地文件夹。

1. 单击“发布” 。

    Visual Studio 生成项目，并将其发布到指定的文件夹。

    发布窗格中显示配置文件摘要。

1. 若要配置部署设置，请单击**设置**摘要的配置文件中。

    ![配置文件设置](../deployment/media/quickstart-profile-settings.png "配置文件设置") 

1. 配置选项，如是否部署 Debug 或 Release 配置，然后单击**保存**。

1. 若要重新发布，请单击**发布**。

可按照任何喜欢的方式部署已发布的文件。 例如，可以在 Zip 文件中将它们打包、 使用一个简单的复制命令，或者将它们部署使用所选的任何安装包。

## <a name="next-steps"></a>后续步骤

- [使用发布工具部署 .NET Core 应用程序](/dotnet/core/deploying/deploy-with-vs)
- [为 Microsoft Store 打包桌面应用（桌面桥）](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)
- (.NET)[部署.NET Framework 和应用程序](/dotnet/framework/deployment/)
