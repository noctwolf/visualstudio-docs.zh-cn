---
title: 如何保留固定的虚拟 IP 地址的 Azure 云服务 |Microsoft Docs
description: 了解如何确保不会更改你的 Azure 云服务的虚拟 IP 地址 (VIP)。
author: ghogen
manager: douge
assetId: 4a58e2c6-7a79-4051-8a2c-99182ff8b881
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/21/2017
ms.author: ghogen
ms.openlocfilehash: e74cc5b9bbbfea92d2dea2c00ee5b0f98dc02f21
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001560"
---
# <a name="retain-a-constant-virtual-ip-address-for-an-azure-cloud-service"></a>保留 Azure 云服务的常用虚拟 IP 地址
当更新在 Azure 中托管的云服务时，可能需要确保该服务的虚拟 IP 地址 (VIP) 不会更改。 许多域管理服务使用域名系统 (DNS) 来注册域名。 仅当 VIP 保持不变，DNS 才适用。 可以使用**发布向导**更新中 Azure 工具，以确保你的云服务的 VIP 不会更改时。 有关如何使用云服务的 DNS 域管理的详细信息，请参阅[配置 Azure 云服务的自定义域名称](/azure/cloud-services/cloud-services-custom-domain-name-portal)。

## <a name="publish-a-cloud-service-without-changing-its-vip"></a>发布云服务，但不更改其 VIP
当你首次将其部署到 Azure 在特定环境中，如生产环境时，云服务的 VIP 就已分配。 仅当显式删除部署或部署更新过程隐式删除部署，VIP 将不同。 若要保留 VIP，则切勿删除你的部署，并必须确保 Visual Studio 不会自动删除您的部署。 

可以指定部署中的设置**发布向导**，它支持多个部署选项。 您可以指定全新部署或更新部署，可以是增量或同时进行。 这两种更新部署都将保留 VIP。 有关部署这些不同类型的定义，请参阅[发布 Azure 应用程序向导](vs-azure-tools-publish-azure-application-wizard.md)。 此外，您可以控制出错时是否删除云服务的以前的部署。 如果未正确设置该选项，VIP 可能会意外更改。

## <a name="update-a-cloud-service-without-changing-its-vip"></a>更新云服务，而无需更改其 VIP
1. 创建或在 Visual Studio 中打开 Azure 云服务项目。 

2. 在中**解决方案资源管理器**，右键单击该项目。 在快捷菜单上，选择**发布**。

    ![发布菜单](./media/vs-azure-tools-cloud-service-retain-a-constant-virtual-ip-address/solution-explorer-publish-menu.png)

3. 在中**发布 Azure 应用程序**对话框框中，选择你想要部署的 Azure 订阅。 如果有必要，然后选择登录**下一步**。

    ![发布 Azure 应用程序登录页](./media/vs-azure-tools-cloud-service-retain-a-constant-virtual-ip-address/azure-publish-signin.png)

4. 上**常用设置**选项卡上，验证要部署到服务的云名称，则**环境**，则**生成配置**，和**服务配置**是否均正确。

    ![发布 Azure 应用程序的常见设置选项卡](./media/vs-azure-tools-cloud-service-retain-a-constant-virtual-ip-address/azure-publish-common-settings.png)

5. 上**高级设置**选项卡上，确认**部署标签**并**存储帐户**正确无误。 确认**失败时删除部署**复选框已清除，并确认**部署更新**复选框处于选中状态。 通过清除**失败时删除部署**复选框，则确保你的 VIP 在部署过程中发生错误时不会丢失。 通过选择**部署更新**复选框，确保你的部署，不会删除并重新发布你的应用程序时，你的 VIP 不会丢失。 

    ![发布 Azure 应用程序高级设置选项卡](./media/vs-azure-tools-cloud-service-retain-a-constant-virtual-ip-address/azure-publish-advanced-settings.png)

6. 若要进一步指定要更新的角色的方式，请选择**设置**旁边**部署更新**。 选择任一**增量更新**或**同时更新**，然后选择**确定**。 选择**增量更新**要更新的应用程序中，每个实例，以便应用程序始终可用。 选择**同时更新**更新的同时在应用程序的所有实例。 同时更新速度更快，但你的服务可能不可用在更新过程。 在完成后，请选择**下一步**。

    ![发布 Azure 应用程序部署设置页](./media/vs-azure-tools-cloud-service-retain-a-constant-virtual-ip-address/azure-publish-deployment-update-settings.png)

7. 在中**发布 Azure 应用程序**对话框中，选择**下一步**直到**摘要**显示页。 验证你的设置，并选择**发布**。
   
    ![发布 Azure 应用程序摘要页](./media/vs-azure-tools-cloud-service-retain-a-constant-virtual-ip-address/azure-publish-summary.png)

## <a name="next-steps"></a>后续步骤
- [使用 Visual Studio 发布 Azure 应用程序向导](vs-azure-tools-publish-azure-application-wizard.md)

