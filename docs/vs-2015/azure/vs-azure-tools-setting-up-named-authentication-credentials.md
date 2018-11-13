---
title: 设置命名的身份验证凭据 |Microsoft Docs
description: 了解如何提供 Visual Studio 可用于请求到 Azure，以便您可以发布到 Azure 应用程序从 Visual Studio 或监视现有云服务进行身份验证的凭据。
author: ghogen
manager: douge
assetId: 61570907-42a1-40e8-bcd6-952b21a55786
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2017
ms.author: ghogen
ms.openlocfilehash: 6f41ea2072ef5791735fac61205f68151d5a9f7e
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001563"
---
# <a name="set-up-named-authentication-credentials"></a>设置命名的身份验证凭据

若要发布到 Azure 的应用程序或监视现有云服务，Visual Studio 需要凭据进行身份验证请求到 Azure，即你的 Azure 订阅 ID 和有效的 X.509 v3 证书使用至少 2048 位的密钥。 提供这些凭据通过以下方法之一：

- 在 Visual Studio 中，选择**视图 > 服务器资源管理器**，右键单击**Azure**节点中，选择**连接到 Microsoft Azure 订阅**，并登录。
- 创建一个订阅文件 (`.publishsettings`)，其中包含公钥的证书。 在本文中所述，该订阅文件可以包含多个订阅的凭据。

注意： 这些凭据是不同于使用 Azure 存储服务的请求进行身份验证的凭据。

## <a name="create-a-subscription-file"></a>创建一个订阅文件

在服务器资源管理器中右键单击**Azure**节点，然后选择**管理和筛选订阅**。 然后选择**证书**选项卡，然后执行以下操作之一：

- 选择**导入**以打开**导入 Microsoft Azure 订阅**对话框。 选择**下载订阅文件**链接，并在浏览器中将下载的文件保存到临时位置。 返回对话框中，浏览到下载位置，然后将其导入用于身份验证。
- 选择一个有效的订阅，然后选择**编辑**，这会打开一个对话框，在其中编辑用于身份验证的现有订阅。
- 选择**新建**以打开**新订阅**对话框框，并提供所需的详细信息。 若要将证书上传到你的云服务中注明了对话框中，登录到 Azure 门户中，导航到云服务，选择**设置 > 管理证书**，选择**上传**，然后指定的路径`.cer`文件。

如果你想要自行创建证书，您可以参考中的说明[创建并上传 Azure 管理证书](https://msdn.microsoft.com/library/windowsazure/gg551722.aspx)到证书，手动上传[Azure 门户](https://portal.azure.com/)。

## <a name="next-steps"></a>后续步骤

- [Web 应用的一般概述](https://docs.microsoft.com/azure/app-service/)
- [将应用部署到 Azure 应用服务](https://docs.microsoft.com/azure/app-service/app-service-deploy-local-git) 
- [使用 Visual Studio 部署 web 作业](https://docs.microsoft.com/azure/app-service/websites-dotnet-deploy-webjobs)
- [创建和部署云服务](https://docs.microsoft.com/azure/cloud-services/cloud-services-how-to-create-deploy-portal)