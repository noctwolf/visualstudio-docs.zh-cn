---
title: 如何将项目升级到当前版本的 Azure 工具 |Microsoft Docs
description: 了解如何在 Visual Studio 中的将 Azure 项目升级到当前版本的 Azure 工具
author: ghogen
manager: douge
assetId: 1d64070a-078d-468a-87f4-e6715de6475f
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/18/2016
ms.author: ghogen
ms.openlocfilehash: c5fb70f2dd09338dd2e2f6b01cb60bf2be0cdbdd
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001562"
---
# <a name="how-to-upgrade-projects-to-the-current-version-of-the-azure-tools-for-visual-studio"></a>如何将项目升级为适用于 Visual Studio 的 Azure 工具的最新版本
## <a name="overview"></a>概述
安装当前版本的 Azure 工具 （或比 1.6 的以前版本） 后，使用 Azure Tools 创建的任何项目版本 1.6 版 (2011 年 11 月) 将自动升级就立即打开它们。 如果使用这些工具的 1.6 (2011 年 11 月) 版本创建的项目，您仍然可以安装该版本，可以在较旧版本中打开这些项目并在以后决定是否要将它们升级。

## <a name="how-your-project-changes-when-you-upgrade-it"></a>你的项目时将其升级的更改
如果项目自动升级，或指定你想要将其升级，你的项目修改为使用当前版本的某些程序集，并也更改某些属性，如本部分介绍。 如果你的项目需要其他更改，才能与较新版本的工具兼容，您必须手动进行这些更改。

* Web.config 文件中的为 web 角色和辅助角色的 app.config 文件更新为引用较新版的 Microsoft.WindowsAzure.Diagnostics.DiagnosticMonitoirTraceListener.dll。
* Microsoft.WindowsAzure.StorageClient.dll、 Microsoft.WindowsAzure.Diagnostics.dll 和 Microsoft.WindowsAzure.ServiceRuntime.dll 程序集将升级到新版本。
* 在 Azure 项目文件 (.ccproj) 中存储的发布配置文件中移动到单独的文件，扩展名为.azurepubxml，**发布**子目录。
* 发布配置文件中的某些属性已更新为支持新功能和更改功能。 **AllowUpgrade**替换为**DeploymentReplacementMethod**因为您可以同时或以增量方式更新已部署的云服务。
* 该属性**UseIISExpressByDefault**添加并设置为 false，以便用于调试的 web 服务器不会自动将从 Internet 信息服务 (IIS) 更改为 IIS Express。 IIS Express 是使用较新版本的工具创建的项目的默认 web 服务器。
* 如果 Azure Caching 托管在一个或多个项目的角色中，项目升级时，会更改服务配置 （.cscfg 文件） 和服务定义 （.csdef 文件） 中的某些属性。 如果项目使用 Azure Caching NuGet 包，该项目升级到最新版本的包。 应该打开 web.config 文件，并验证客户端配置时正确保留在升级过程中。 如果不使用 NuGet 包添加对 Azure Caching 的客户端程序集的引用，将不更新这些程序集;您必须手动更新这些对新版本的引用。

> [!IMPORTANT]
> 有关F#项目中，您必须手动更新对 Azure 程序集的引用，以便它们引用这些程序集的较新版本。
> 
> 

### <a name="how-to-upgrade-an-azure-project-to-the-current-release"></a>如何将 Azure 项目升级到当前版本
1. 将当前版本的 Azure Tools 安装到你想要用于已升级项目的 Visual Studio 的安装，然后打开你想要升级的项目。 如果项目创建使用 Azure Tools 1.6 版 (2011 年 11 月)，项目将自动升级到最新版本。 如果该项目已创建使用 2011 年 11 月版本和仍然安装该版本，在该版本中打开该项目。
2. 在解决方案资源管理器，打开项目节点的快捷菜单，选择**属性**，然后选择**应用程序**出现的对话框选项卡。
   
    **应用程序**选项卡显示与项目关联的工具版本。 显示 Azure Tools 的当前版本，如果已升级项目。 如果已安装的工具版本比选项卡所示，更新**升级**按钮将出现。
3. 选择**升级**按钮以将项目升级到当前版本的工具。
4. 生成项目，然后解决任何错误，从而导致从 API 更改。 有关如何修改代码，使新版本的信息，请参阅特定 API 的文档。

