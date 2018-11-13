---
title: 准备发布或部署云服务从 Visual Studio |Microsoft Docs
description: 了解设置云服务和存储帐户服务和配置 Azure 应用程序的过程。
author: ghogen
manager: douge
ms.assetid: 92ee2f9e-ec49-4c7a-900d-620abe5e9d8a
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/10/2017
ms.author: ghogen
ms.openlocfilehash: d7643d87f60b953b9c0928571036c7890e4d11f0
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001576"
---
# <a name="prepare-to-publish-or-deploy-a-cloud-service-from-visual-studio"></a>准备从 Visual Studio 发布或部署云服务

若要发布云服务项目，你必须设置以下服务在本文中所述：

* 一个**云服务**用于在 Azure 环境中运行角色和 
* 一个**存储帐户**，它提供对 Blob、 队列和表服务的访问。

## <a name="create-a-cloud-service"></a>创建云服务

云服务在 Azure 环境中运行你的角色。 可以创建云服务在 Visual Studio 中或通过[Azure 门户](https://portal.azure.com/)以下各节中所述。

### <a name="create-a-cloud-service-from-visual-studio"></a>从 Visual Studio 创建云服务

1. 使用以前创建的云服务项目，右键单击该项目并选择**发布**。
1. 如有必要，使用 Microsoft 或与你的 Azure 订阅相关联的组织帐户登录，然后选择**下一步**转到**设置**页。
1. 一个**创建云服务和存储帐户**此时将显示对话框 (如果没有，选择**创建新**从**云服务**列表)。
1. 输入你的云服务的窗体 URL 的一部分，并且必须是唯一的不区分大小写名称。 此外选择区域或地缘组，然后选择复制选项。

### <a name="create-a-cloud-service-through-the-azure-portal"></a>创建云服务通过 Azure 门户

1. 登录 [Azure 门户](https://portal.azure.com/)。
1. 选择**云服务 （经典）** 在页面的左侧。
1. 选择 **+ 添加**，然后提供所需的信息 （DNS 名称、 订阅、 资源组和位置）。 不需要在此时上载包，因为更高版本在 Visual Studio 中执行的操作。
1. 选择**创建**以完成过程。

## <a name="create-a-storage-account"></a>创建存储帐户

存储帐户提供对 Blob、 队列和表服务的访问。 可以创建存储帐户通过 Visual Studio 或[Azure 门户](https://portal.azure.com/)。

### <a name="create-a-storage-account-from-visual-studio"></a>从 Visual Studio 中创建存储帐户

1. 在中**解决方案资源管理器**使用以前创建的云服务项目中，找到**连接的服务**中角色项目，右键单击，并选择节点**添加连接的服务**. (在 Visual Studio 2015 中，右键单击**存储**节点，然后选择**创建存储帐户**。)
1. 在中**连接的服务**显示列表中，选择**使用 Azure 存储的云存储**。
1. 在 Azure 存储出现的对话框中，选择 **+ 创建新的存储帐户**，这会打开一个对话框，在其中指定你的订阅，名称帐户 fo、 定价层、 资源组和位置。
1. 选择**创建**完成后。 新的存储帐户出现在订阅中可用的存储帐户的列表中。
1. 选择该帐户并选择**添加**。

### <a name="create-a-storage-account-through-the-azure-portal"></a>创建存储帐户通过 Azure 门户

1. 登录 [Azure 门户](https://portal.azure.com/)。
1. 选择 **+ 新建**左上角。
1. 选择**存储**在"Azure Marketplace 中，"然后**存储帐户-blob、 文件、 表、 队列**从右侧。
1. 提供所需的信息 （名称、 部署模型中，等。
1. 选择**创建**以完成过程。

## <a name="configure-your-app-to-use-the-storage-account"></a>将应用配置为使用存储帐户

创建存储帐户后，会自动连接到它从 Visual Studio 更新项目，包括 Url 和访问密钥的服务的配置。

如果创建云服务从 Visual Studio 中使用**添加连接的服务**，可以通过打开检查连接`ServiceConfiguration.Cloud.cscfg`和`ServiceConfiguration.Local.cscfg`。

如果创建云服务通过 Azure 门户，按照中的相同步骤[Visual Studio 中创建存储帐户](#create-a-storage-account-from-visual-studio)但选择现有帐户而不是创建一个新。 然后，visual Studio 更新你的配置。

若要配置设置手动，使用属性页中 Visual Studio 云服务项目中的适用角色 (右键单击角色并选择**属性**)。 有关详细信息，请参阅[配置存储帐户的连接字符串](vs-azure-tools-multiple-services-project-configurations.md#configuring-a-connection-string-for-a-storage-account)。

### <a name="about-access-keys"></a>有关访问密钥

在 Azure 门户显示了可用于访问每个 Azure 存储服务，以及你的帐户的主要和辅助访问密钥中的资源的 Url。 使用这些密钥进行身份验证对存储服务发出的请求。

辅助访问密钥提供到您的存储帐户的主访问密钥与相同的访问，并生成作为备份你的主访问密钥会泄露。 此外，建议你定期进行的访问密钥重新生成。 可以修改连接字符串设置为使用辅助密钥，同时重新生成主密钥，则你可以修改它以使用重新生成主要密钥，同时重新生成辅助密钥。

## <a name="next-steps"></a>后续步骤

若要了解有关将应用发布到 Azure 从 Visual Studio，请参阅[发布云服务使用 Azure Tools](vs-azure-tools-publishing-a-cloud-service.md)。
