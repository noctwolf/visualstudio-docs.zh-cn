---
title: 发布云服务使用的 Azure 工具 |Microsoft Docs
description: 了解有关如何使用 Visual Studio 发布 Azure 云服务项目。
author: ghogen
manager: douge
assetId: 1a07b6e4-3678-4cbf-b37e-4520b402a3d9
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2017
ms.author: ghogen
ms.openlocfilehash: cf29e1cdde71d2e8ef7caa9bc91bc31c30c7bc41
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001552"
---
# <a name="publishing-a-cloud-service-using-visual-studio"></a>使用 Visual Studio 发布云服务

Visual Studio 可以将发布到 Azure，同时对云服务的过渡和生产环境的支持直接的应用程序。 在发布时，你选择部署环境和临时用于部署包的存储帐户。

当你在开发和测试 Azure 应用程序时，可以使用 Web 部署以增量方式发布更改为 web 角色。 发布到部署环境的应用程序后，Web 部署允许您直接到虚拟机中运行 web 角色的部署的更改。 无需打包和发布整个 Azure 应用程序每次想要更新 web 角色以测试更改。 使用此方法时，您可以在 web 角色更改可在云中进行测试而无需等待应用程序发布到部署环境中。

若要发布 Azure 应用程序，并使用 Web 部署来更新 web 角色，请使用以下过程：

- 发布或打包 Azure 应用程序从 Visual Studio
- 更新 web 角色作为开发和测试周期的一部分

## <a name="publish-or-package-an-azure-application-from-visual-studio"></a>发布或打包 Azure 应用程序从 Visual Studio

当发布 Azure 应用程序时，可以执行以下任务之一：

- 创建服务包： 可以使用此包和服务配置文件发布到部署环境从应用程序[Azure 门户](https://portal.azure.com)。

- 发布 Azure 项目从 Visual Studio： 要发布到 Azure 的直接应用程序，请使用发布向导。 有关信息，请参阅[发布 Azure 应用程序向导](vs-azure-tools-publish-azure-application-wizard.md)。

### <a name="to-create-a-service-package-from-visual-studio"></a>若要从 Visual Studio 创建服务包

1. 当准备好发布应用程序，打开解决方案资源管理器，打开包含你的角色的 Azure 项目的快捷菜单并选择发布。

1. 若要创建服务包，请执行以下步骤：

   a. 在 Azure 项目的快捷菜单，选择**包**。

   b. 在中**打包 Azure 应用程序**对话框中，选择你想要创建的包的服务配置，然后选择生成配置。

   c. （可选）若要打开远程桌面的云服务发布之后为它，选择**为所有角色启用远程桌面**，然后选择**设置**来配置远程桌面凭据。 有关详细信息，请参阅[使用 Visual Studio 的 Azure 云服务中的角色启用远程桌面连接](/azure/cloud-services/cloud-services-role-enable-remote-desktop-visual-studio)。

      如果你想要调试你的云服务发布之后为它，将通过选择远程调试**为所有角色启用远程调试器**。

   d. 若要创建包，请选择**包**链接。

      文件资源管理器显示新创建的包的文件位置。 可以复制此位置，以便可以从 Azure 门户中使用。

   e. 若要将此包发布到部署环境，必须使用此位置作为包位置，当创建云服务，并将此包部署到使用 Azure 门户的环境。

1. （可选）若要取消部署过程中，在活动日志中的行项目的快捷菜单上选择**取消并删除**。 此命令会停止部署过程，并从 Azure 中删除部署环境。 若要在部署后删除环境，请使用 Azure 门户。

1. （可选）角色实例启动后，Visual Studio 将自动显示部署环境**云服务**服务器资源管理器中的节点。 在这里，您可以查看单个角色实例的状态。 请参阅[使用云资源管理器管理 Azure 资源](vs-azure-tools-resources-managing-with-cloud-explorer.md)。下图显示了角色实例时仍处于正在初始化状态：

    ![VST_DeployComputeNode](./media/vs-azure-tools-publishing-a-cloud-service/IC744134.png)

## <a name="update-a-web-role-as-part-of-the-development-and-testing-cycle"></a>更新 web 角色作为开发和测试周期的一部分

如果你的应用的后端基础结构是稳定的但 web 角色需要更加频繁更新，可以使用 Web 部署来更新 web 角色项目中。 如果不希望重新生成并重新部署后端辅助角色，或如果你有多个 web 角色，并且你想要更新 web 角色之一，web 部署会非常方便。

### <a name="requirements-for-using-web-deploy"></a>使用 Web 部署的要求

- **仅用于开发和测试目的**： 更改直接到虚拟机正在其中运行 web 角色。 如果此虚拟机必须被回收，所做的更改将丢失，因为你发布的原始包用于重新创建角色的虚拟机。 重新发布应用程序以获取最新更改 web 角色。

- **仅 web 角色可以更新**： 无法更新辅助角色。 此外，不能更新`RoleEntryPoint`在`web role.cs`。

- **只能支持 web 角色的单个实例**： 不能在部署环境中有任何？ eb 角色的多个实例。 但是，支持多个 web 角色只有一个实例。

- **启用远程桌面连接**： 此要求，Web 部署可以使用的用户名和密码连接到虚拟机将部署到运行 Internet 信息服务 (IIS) 服务器所做的更改。 此外，您可能需要连接到虚拟机，若要将此虚拟机上的受信任的证书添加到 IIS。 （此证书可以确保 Web 部署使用的 iis 远程连接是安全的。）

以下过程假定您使用的**发布 Azure 应用程序**向导。

### <a name="enable-web-deploy-when-you-publish-your-application"></a>启用 Web 部署发布应用程序时

1. 若要启用**为所有 web 角色启用 Web 部署**选项，必须首先配置远程桌面连接。 选择**启用远程桌面**为所有角色，然后将提供用于在远程连接的凭据**远程桌面配置**出现框。 请参阅[使用 Visual Studio 的 Azure 云服务中的角色启用远程桌面连接](/azure/cloud-services/cloud-services-role-enable-remote-desktop-visual-studio)。

1. 若要在应用程序中的所有 web 角色都启用 Web 部署，请选择**为所有 web 角色都启用 Web 部署**。

    显示黄色警告三角形。 Web 部署使用默认情况下不建议上传敏感数据不受信任的自签名证书。 如果您需要保护敏感数据的进程，可以添加要用于 Web 部署连接的 SSL 证书。 此证书必须是受信任的证书。 有关详细信息，请参阅[确保 web 部署安全](#make-web-deploy-secure)。

1. 选择**下一步**以显示**摘要**屏幕上，，然后选择**发布**部署云服务。

    发布云服务。 创建虚拟机已启用 iis，以便 Web 部署可用于更新而无需重新发布它们的 web 角色的远程连接。

   > [!NOTE]
   > 如果为 web 角色配置的多个实例，则会显示一条警告消息，指出每个 web 角色仅限于仅在为发布你的应用程序而创建的包中的一个实例。 选择**确定**以继续。 因为要求部分中所述，可以有多个 web 角色，但每个角色只有一个实例。

### <a name="update-your-web-role-by-using-web-deploy"></a>使用 Web 部署来更新 web 角色

1. 若要使用 Web 部署，对任何你想要发布，然后右键单击你的解决方案中的此项目节点并指向的 Visual Studio 中的 web 角色项目进行代码更改**发布**。 **发布 Web**对话框随即出现。

1. （可选）如果添加受信任的 SSL 证书用于 IIS 的远程连接，则可以清除**允许不受信任的证书**复选框。 有关如何添加证书以确保 Web 部署安全的信息，请参阅明**确保 Web 部署安全**这篇文章中更高版本。

1. 若要使用 Web 部署，发布机制需要使用用户名和密码用于远程桌面连接时设置在首次发布包。

   a. 在中**用户名**，输入用户名称。

   b. 在中**密码**，输入的密码。

   c. （可选）如果你想要将此密码保存此配置文件中，选择**保存密码**。

1. 若要将所做的更改发布到你的 web 角色中，选择**发布**。

    状态行显示**发布已启动**。 发布完成后，**发布成功**出现。 所做的更改现在已部署到你的虚拟机上的 web 角色。 现在，您可以开始测试所做的更改在 Azure 环境中 Azure 应用程序。

### <a name="make-web-deploy-secure"></a>确保 web 部署安全

1. Web 部署使用默认情况下不建议上传敏感数据不受信任的自签名证书。 如果您需要保护敏感数据的进程，可以添加要用于 Web 部署连接的 SSL 证书。 此证书必须是受信任的证书，证书颁发机构 (CA) 获取。

    若要确保 Web 部署安全的每个虚拟机的每个 web 角色，必须上传受信任的证书，你想要用于 web 部署到 Azure 门户。 此证书可以确保该证书已添加到发布应用程序时，为 web 角色创建虚拟机。

1. 若要将受信任的 SSL 证书添加到 IIS 以用于远程连接，请执行以下步骤：

   a. 若要连接到运行 web 角色的虚拟机，请选择中的 web 角色的实例**云资源管理器**或**服务器资源管理器**，然后选择**使用远程桌面连接**命令。 有关如何连接到虚拟机的详细步骤，请参阅[使用 Visual Studio 的 Azure 云服务中的角色启用远程桌面连接](/azure/cloud-services/cloud-services-role-enable-remote-desktop-visual-studio)。 在浏览器会提示你下载`.rdp`文件。

   b. 若要添加的 SSL 证书，请打开管理服务在 IIS 管理器。 在 IIS 管理器中，通过打开启用 SSL**绑定**中的链接**操作**窗格。 **添加网站绑定**对话框随即出现。 选择**外**，然后选择在 HTTPS**类型**下拉列表。 在中**SSL 证书**列表中，选择必须由 CA 签名并上载到 Azure 门户的 SSL 证书。 有关详细信息，请参阅[配置管理服务的连接设置](http://go.microsoft.com/fwlink/?LinkId=215824)。

      > [!NOTE]
      > 如果添加受信任的 SSL 证书，请在中不再显示黄色警告三角形**发布向导**。

## <a name="include-files-in-the-service-package"></a>服务包中包含文件

您可能需要在服务包中包括特定的文件，以便可以为角色创建虚拟机上可用。 例如，你可能想要添加`.exe`或`.msi`到服务包的启动脚本使用的文件。 或者，可能需要添加 web 角色或辅助角色项目所需的程序集。 要包括的文件，必须将它们添加到 Azure 应用程序的解决方案。

1. 若要将程序集添加到服务包，请使用以下步骤：

   a. 在中**解决方案资源管理器**，打开缺少已引用程序集的项目的项目节点。
   b. 若要将程序集添加到项目中，打开快捷菜单**引用**文件夹，然后选择**添加引用**。 此时将显示添加引用对话框。
   c. 选择你想要添加，然后选择的引用**确定**。 将引用添加到下的列表**引用**文件夹。
   d. 打开您添加的程序集的快捷菜单，然后选择**属性**。 **属性**窗口会显示。

      若要在服务包中，此程序集包含在**复制本地列表**选择**True**。
1. 在中**解决方案资源管理器**打开缺少已引用程序集的项目的项目节点。

1. 若要将程序集添加到项目中，打开快捷菜单**引用**文件夹，然后选择**添加引用**。 **添加引用**此时将显示对话框。

1. 选择你想要添加，然后选择的引用**确定**按钮。

    将引用添加到下的列表**引用**文件夹。

1. 打开您添加的程序集的快捷菜单，然后选择**属性**。 属性窗口会显示。

1. 若要在服务包中，此程序集包含在**Copy Local**列表中，选择**True**。

1. 若要在已添加到你的 web 角色项目的服务包中包含文件，打开该文件的快捷菜单，然后选择**属性**。 从**属性**窗口中，选择**内容**从**生成操作**列表框。

1. 若要在已添加到辅助角色项目的服务包中包含文件，打开该文件的快捷菜单，然后选择**属性**。 从**属性**窗口中，选择**如果较新则复制**从**复制到输出目录**列表框。

## <a name="next-steps"></a>后续步骤

若要了解详细信息发布到 Azure 从 Visual Studio，请参阅[发布 Azure 应用程序向导](vs-azure-tools-publish-azure-application-wizard.md)。
