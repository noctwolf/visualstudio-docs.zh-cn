---
title: 如何管理服务配置和配置文件 |Microsoft Docs
description: 了解如何使用服务配置和配置文件配置文件 |该存储设置的部署环境和发布云服务的设置。
author: ghogen
manager: douge
assetId: 7da8c551-fb06-4057-b5c7-c77f4b39d803
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 8/11/2017
ms.author: ghogen
ms.openlocfilehash: 3f7c7341b115f0899ac4c90d574a65dfdb4087bc
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001564"
---
# <a name="how-to-manage-service-configurations-and-profiles"></a>如何管理服务配置和配置文件
## <a name="overview"></a>概述
Visual Studio 发布云服务时，将配置信息存储在两种类型的配置文件中： 服务配置和配置文件。 服务配置 （.cscfg 文件） 存储 Azure 云服务的部署环境设置。 管理你的云服务时，azure 将使用这些配置文件。 但是，配置文件 （.azurePubxml 文件） 存储区将发布云服务的设置。 这些设置是一条记录所做的选择时使用发布向导中，并由 Visual Studio 在本地使用。 本主题说明如何使用这两种类型的配置文件。

## <a name="service-configurations"></a>服务配置
可以创建多个服务配置要用于每个部署环境。 例如，可能会创建用于运行和测试 Azure 应用程序和另一个服务配置为生产环境的本地环境的服务配置。

您可以添加、 删除、 重命名和修改基于自身要求这些服务配置。 下图中所示，可以从 Visual Studio 中管理这些服务配置。

![管理服务配置](./media/vs-azure-tools-service-configurations-and-profiles-how-to-manage/manage-service-config.png)

此外可以打开**管理配置**从角色的属性页对话框。 若要在 Azure 项目中打开角色的属性，请打开该角色的快捷菜单，然后选择**属性**。 上**设置**选项卡上，展开**服务配置**列表，并选择**管理**以打开**管理配置**对话框。

### <a name="to-add-a-service-configuration"></a>若要添加的服务配置
1. 在解决方案资源管理器中打开 Azure 项目的快捷菜单，然后选择**管理配置**。
   
    **管理服务配置**对话框随即出现。
2. 若要添加的服务配置，必须创建一份现有配置。 若要执行此操作，选择你想要从名称列表中复制，然后选择的配置**创建副本**。
3. （可选）要为服务配置不同的名称，从名称列表中选择新的服务配置，然后选择**重命名**。 在中**名称**文字框中，键入你想要用于此服务配置，然后选择**确定**。
   
    名为服务配置一个新服务配置文件。[New Name].cscfg 添加到解决方案资源管理器中的 Azure 项目。

### <a name="to-delete-a-service-configuration"></a>若要删除服务配置
1. 在解决方案资源管理器中打开 Azure 项目的快捷菜单，然后选择**管理配置**。
   
    **管理服务配置**对话框随即出现。
2. 若要删除服务配置，选择你想要从删除的配置**名称**列表，然后选择**删除**。 对话框将出现以确认要删除此配置。
3. 选择**删除**。
   
     服务配置文件已从解决方案资源管理器中的 Azure 项目。

### <a name="to-rename-a-service-configuration"></a>若要重命名服务配置
1. 在解决方案资源管理器，打开 Azure 项目的快捷菜单，然后选择**管理配置**。
   
    **管理服务配置**对话框随即出现。
2. 若要重命名服务配置，请选择从新的服务配置**名称**列表，并选择**重命名**。 在中**名称**文字框中，键入你想要用于此服务配置，然后选择**确定**。
   
    在解决方案资源管理器中的 Azure 项目中更改服务配置文件的名称。

### <a name="to-change-a-service-configuration"></a>若要更改服务配置
* 如果你想要更改服务配置，打开你想要在 Azure 项目中，更改，然后选择的特定角色的快捷菜单**属性**。 请参阅[如何： 使用 Visual Studio 为 Azure 云服务配置的角色](vs-azure-tools-configure-roles-for-cloud-service.md)有关详细信息。

## <a name="make-different-setting-combinations-by-using-profiles"></a>使用配置文件进行不同设置组合
通过使用配置文件，您可以自动填入**发布向导**使用目的不同设置的不同组合。 例如，可以有一个配置文件用于调试和另一个用于发布生成。 在这种情况下，你**调试**配置文件应已**IntelliTrace**启用并**调试**配置选择，和你**版本**配置文件应已**IntelliTrace**禁用并**发行**所选配置。 此外可以使用不同的配置文件部署使用不同的存储帐户的服务。

第一次运行向导，创建默认配置文件。 Visual Studio 已添加到 Azure 项目在扩展名为.azurePubXml 的文件中存储的配置文件**配置文件**文件夹。 如果稍后运行向导时，手动指定其他选项，该文件会自动更新。 运行以下过程之前，你应已发布你的云服务在至少一次。

### <a name="to-add-a-profile"></a>若要添加的配置文件
1. 打开 Azure 项目的快捷菜单，然后选择**发布**。
2. 下一步**目标配置文件**列表中，选择**保存配置文件**按钮，如下图所示。 这将为您创建一个配置文件。
   
    ![创建新的配置文件](./media/vs-azure-tools-service-configurations-and-profiles-how-to-manage/create-new-profile.png)
3. 创建配置文件后，选择 **< 管理...> >** 中**目标配置文件**列表。
   
    **管理配置文件**出现对话框，如下图所示。
   
    ![管理配置文件对话框](./media/vs-azure-tools-service-configurations-and-profiles-how-to-manage/manage-profiles.png)
4. 在中**名称**列表中，选择一个配置文件，然后选择**创建副本**。
5. 选择**关闭**按钮。
   
    新的配置文件将出现在目标配置文件列表。
6. 在中**目标配置文件**列表中，选择刚创建的配置文件。 使用所选的配置文件中的选择填充发布向导的设置。
7. 选择**上一步**并**下一步**按钮以显示发布向导中，每一页，然后自定义此配置文件的设置。 请参阅[发布 Azure 应用程序向导](http://go.microsoft.com/fwlink/p/?LinkID=623085)有关信息。
8. 完成自定义设置后，选择**下一步**以返回到设置页。 通过使用这些设置发布服务时，或者如果您选择保存该配置文件**保存**旁边的配置文件列表。

### <a name="to-rename-or-delete-a-profile"></a>若要重命名或删除配置文件
1. 打开 Azure 项目的快捷菜单，然后选择**发布**。
2. 在中**目标配置文件**列表中，选择**管理**。
3. 在中**管理配置文件**对话框中，选择你想要删除的配置文件，然后选择**删除**。
4. 在出现确认对话框中，选择**确定**。
5. 选择**关闭**。

### <a name="to-change-a-profile"></a>若要更改一个配置文件
1. 打开 Azure 项目的快捷菜单，然后选择**发布**。
2. 在中**目标配置文件**列表中，选择你想要更改的配置文件。
3. 选择**上一步**并**下一步**按钮显示发布向导中，每一页，然后更改所需的设置。 请参阅[发布 Azure 应用程序向导](http://go.microsoft.com/fwlink/p/?LinkID=623085)有关信息。
4. 完成更改设置后，选择**下一步**若要回到**设置**页。
5. （可选） 选择**发布**发布云服务使用新的设置。 如果不想在此时，发布你的云服务，并且关闭发布向导，Visual Studio 会要求你想要将所做的更改保存到配置文件。

## <a name="next-steps"></a>后续步骤
若要了解如何配置 Azure 项目从 Visual Studio 的其他部分，请参阅[配置 Azure 项目](http://go.microsoft.com/fwlink/p/?LinkID=623075)

