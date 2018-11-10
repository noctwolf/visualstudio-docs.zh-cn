---
title: 使用 Azure 资源组项目的 Azure DevOps 服务中的持续集成 |Microsoft Docs
description: 介绍如何在 Visual Studio 中使用 Azure 资源组部署项目设置持续集成中 Azure DevOps 服务。
author: mlearned
manager: douge
ms.assetid: b81c172a-be87-4adc-861e-d20b94be9e38
ms.service: azure-resource-manager
ms.topic: article
ms.workload: azure-vs
ms.date: 08/01/2016
ms.author: mlearned
ms.openlocfilehash: f6404b15e8a7cd3f95ac63bbae6076ef62fcff06
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001582"
---
# <a name="continuous-integration-in-azure-devops-services-using-azure-resource-group-deployment-projects"></a>使用 Azure 资源组部署项目的 Azure DevOps 服务中的持续集成
若要部署 Azure 模板，您执行任务在各个阶段： 生成、 测试、 复制到 Azure （也称为"暂存"），并部署模板。 有两种不同方法，将模板部署到 Azure DevOps 服务。 这两种方法提供相同的结果，因此请选择最适合您的工作流。

1. 生成管道运行的 Azure 资源组部署项目 (Deploy-AzureResourceGroup.ps1) 中包含的 PowerShell 脚本中添加一个步骤。 该脚本将复制项目并部署模板。
2. 添加多个 Azure DevOps 服务生成的步骤，每个执行一个阶段任务。

本文演示了这两个选项。 第一个选项已使用 Visual Studio 中的开发人员和提供一致性的整个生命周期使用的同一个脚本的优点。 第二个选项提供一个便捷替代方式为内置脚本。 这两个过程假定您已经有 Visual Studio 部署项目签入到 Azure DevOps 服务。

## <a name="copy-artifacts-to-azure"></a>将项目复制到 Azure
无论何种方案，如果有任何项目所需的模板部署，则必须向 Azure 资源管理器访问它们。 这些项目可以包括以下文件：

* 嵌套的模板
* 配置脚本和 DSC 脚本
* 应用程序二进制文件

### <a name="nested-templates-and-configuration-scripts"></a>嵌套的模板和配置脚本
当使用 Visual Studio 提供的模板 （或使用 Visual Studio 代码段生成），PowerShell 脚本不仅暂存项目，它还使不同的部署的资源的 URI 参数化。 该脚本，然后将项目复制到 Azure 中的安全容器、 创建该容器的 SaS 令牌，然后将模板部署到该信息传递。 请参阅[创建模板部署](https://msdn.microsoft.com/library/azure/dn790564.aspx)若要了解有关嵌套模板的详细信息。  当使用 Azure DevOps 服务中的任务，必须为模板部署选择适当的任务，并如有必要，请将暂存步骤中传递参数值，模板部署到。

## <a name="set-up-continuous-deployment-in-azure-pipelines"></a>设置 Azure 管道中的连续部署
若要在 Azure 管道中调用 PowerShell 脚本，需要更新生成管道。 简单地说，步骤如下： 

1. 编辑生成管道。
2. 设置 Azure 管道中的 Azure 授权。
3. 添加一个引用 Azure 资源组部署项目中的 PowerShell 脚本的 Azure PowerShell 生成步骤。
4. 设置的值 *-ArtifactsStagingDirectory*参数以使用 Azure 管道中生成的项目。

### <a name="detailed-walkthrough-for-option-1"></a>选项 1 详细的演练
以下过程将引导你完成使用的单个任务，在项目中运行 PowerShell 脚本的 Azure DevOps 服务中配置连续部署所需的步骤。 

1. 编辑 Azure DevOps 服务生成管道并添加 Azure PowerShell 生成步骤。 选择在生成管道**生成管道**类别，然后选择**编辑**链接。
   
   ![编辑生成管道][0]
2. 添加一个新**Azure PowerShell**生成到生成管道的步骤，然后选择**添加生成步骤...** 按钮。
   
   ![添加生成步骤][1]
3. 选择**部署任务**类别中，选择**Azure PowerShell**任务，并选择其**添加**按钮。
   
   ![添加任务][2]
4. 选择**Azure PowerShell**生成步骤，并填充其值。
   
   1. 如果已添加到 Azure DevOps 服务将 Azure 服务终结点，选择要在订阅**Azure 订阅**下拉列表框，然后跳到下一节。 
      
      如果没有 Azure 服务终结点中 Azure DevOps 服务，您需要添加一个。 本小节将引导您完成过程。 如果你的 Azure 帐户使用 Microsoft 帐户 （例如 Hotmail)，必须执行以下步骤以获取服务主体身份验证。

   2. 选择**管理**链接旁边**Azure 订阅**下拉列表框。
      
      ![管理 Azure 订阅][3]
   3. 选择**Azure**中**新建服务终结点**下拉列表框。
      
      ![新建服务终结点][4]
   4. 在中**添加 Azure 订阅**对话框中，选择**服务主体**选项。
      
      ![服务主体选项][5]
   5. 添加到 Azure 订阅信息**添加 Azure 订阅**对话框。 需要提供以下各项：
      
      * 订阅 Id
      * 订阅名称
      * 服务主体 Id
      * 服务主体键
      * 租户 Id
   6. 添加到所选的名称**订阅**名称框。 此值会更高版本显示在**Azure 订阅**Azure DevOps 服务中的下拉列表。 

   7. 如果不知道你的 Azure 订阅 ID，可以使用以下命令之一来对其进行检索。
      
      对于 PowerShell 脚本，请使用：
      
      `Get-AzureRmSubscription`
      
      对于 Azure CLI，请使用：
      
      `azure account show`
   8. 若要获取服务主体 ID、 服务主体密钥和租户 ID，请遵循该过程中[创建 Active Directory 应用程序和服务主体使用门户](/azure/azure-resource-manager/resource-group-create-service-principal-portal)或[与 Azure 服务主体进行身份验证资源管理器](/azure/azure-resource-manager/resource-group-authenticate-service-principal)。
   9. 添加到服务主体 ID、 服务主体密钥和租户 ID 的值**添加 Azure 订阅**对话框框，然后选择**确定**按钮。
      
      您现在拥有有效的服务主体，用于运行 Azure PowerShell 脚本。
5. 编辑生成管道，并选择**Azure PowerShell**生成步骤。 选择在订阅**Azure 订阅**下拉列表框。 (如果订阅未出现，请选择**刷新**按钮**管理**链接。) 
   
   ![配置 Azure PowerShell 生成任务][8]
6. 提供 Deploy-AzureResourceGroup.ps1 PowerShell 脚本的路径。 若要执行此操作，选择省略号 （...） 按钮旁边**脚本路径**框中，导航到中的 Deploy-AzureResourceGroup.ps1 PowerShell 脚本**脚本**文件夹的项目中，选择它，然后选择**确定**按钮。    
   
   ![选择脚本的路径][9]
7. 选择该脚本后，路径更新为该脚本，以便从 Build.StagingDirectory 运行 (相同的目录的*ArtifactsLocation*设置为)。 您可以执行此操作通过添加"$（build.stagingdirectory） /"到脚本路径的开头。
   
    ![编辑脚本的路径][10]
8. 在中**脚本参数**框中，输入以下参数 （在单个行）。 在 Visual Studio 中运行脚本时，可以看到 VS 如何使用中的参数**输出**窗口。 您可以作为起始点使用此生成步骤中设置参数值。
   
   | 参数 | 描述 |
   | --- | --- |
   | -ResourceGroupLocation |资源组所在的位置，例如地理位置值**eastus**或 **'East US'**。 （添加单引号，如果名称中没有空格）。请参阅[Azure 区域](https://azure.microsoft.com/regions/)有关详细信息。 |
   | -ResourceGroupName |用于此部署的资源组的名称。 |
   | -UploadArtifacts |此参数，当存在时，指定需要从本地系统上传到 Azure 的项目。 只需设置此开关，如果您的模板部署需要你想要使用 （例如配置脚本或嵌套的模板） 的 PowerShell 脚本暂存其他项目。 |
   | -StorageAccountName |为此部署到阶段项目使用的存储帐户的名称。 当暂存用于部署的项目，才使用此参数。 如果提供此参数，如果该脚本尚未创建一个在以前的部署过程中创建新的存储帐户。 如果指定了参数，必须已存在的存储帐户。 |
   | -StorageAccountResourceGroupName |与存储帐户关联的资源组的名称。 此参数是必需的仅当为 StorageAccountName 参数提供值。 |
   | -TemplateFile |Azure 资源组部署项目中的模板文件路径。 为了提高灵活性，相对于 PowerShell 脚本而不是绝对路径的位置是此参数使用一个路径。 |
   | -TemplateParametersFile |Azure 资源组部署项目中的参数文件路径。 为了提高灵活性，相对于 PowerShell 脚本而不是绝对路径的位置是此参数使用一个路径。 |
   | ArtifactStagingDirectory |可以使用此参数的 PowerShell 脚本知道应从中复制项目的二进制文件的文件夹。 此值将覆盖使用 PowerShell 脚本的默认值。 对于使用 Azure DevOps 服务，将值设置为： ArtifactStagingDirectory $ （build.stagingdirectory) |
   
   下面是脚本参数示例 （行中断以提高可读性）：
   
   ```    
   -ResourceGroupName 'MyGroup' -ResourceGroupLocation 'eastus' -TemplateFile '..\templates\azuredeploy.json' 
   -TemplateParametersFile '..\templates\azuredeploy.parameters.json' -UploadArtifacts -StorageAccountName 'mystorageacct' 
   –StorageAccountResourceGroupName 'Default-Storage-EastUS' -ArtifactStagingDirectory '$(Build.StagingDirectory)'    
   ```
   
   当您结束，**脚本参数**框应类似于下面的列表：
   
   ![脚本参数][11]
9. 所需的所有项都添加到 Azure PowerShell 生成步骤后，请选择**队列**生成器按钮以生成项目。 **生成**屏幕显示 PowerShell 脚本的输出。

### <a name="detailed-walkthrough-for-option-2"></a>选项 2 详细的演练
以下过程将引导你完成使用内置的任务的 Azure DevOps 服务中配置连续部署所需的步骤。

1. 编辑 Azure DevOps 服务生成管道添加两个新生成步骤。 选择在生成管道**生成定义**类别，然后选择**编辑**链接。
   
   ![编辑生成定义][12]
2. 将新的生成步骤添加到生成中的管道使用**添加生成步骤...** 按钮。
   
   ![添加生成步骤][13]
3. 选择**部署**任务类别中，选择**Azure 文件复制**任务，并选择其**添加**按钮。
   
   ![添加 Azure 文件复制任务][14]
4. 选择**Azure 资源组部署**任务，然后选择其**添加**按钮，然后**关闭****任务目录**。
   
   ![添加 Azure 资源组部署任务][15]
5. 选择**Azure 文件复制**任务，并填充其值。
   
   如果已添加到 Azure DevOps 服务将 Azure 服务终结点，选择要在订阅**Azure 订阅**下拉列表框。 如果还没有订阅，请参阅[选项 1](#detailed-walkthrough-for-option-1)有关在 Azure DevOps 服务中设置的说明。
   
   * 源-输入 **$ （build.stagingdirectory)**
   * Azure 连接类型-选择**Azure 资源管理器**
   * Azure RM 订阅-选择你想要在中使用的存储帐户的订阅**Azure 订阅**下拉列表框。 如果订阅未出现，请选择**刷新**按钮**管理**链接。
   * 目标类型-选择**Azure Blob**
   * RM 存储帐户-选择你的存储帐户想要用于暂存项目
   * 容器名称-输入想要用于暂存; 的容器的名称它可以是任何有效的容器名称，但使用一个专用于此生成管道
   
   对于输出值：
   
   * 存储容器 URI-输入**artifactsLocation**
   * 存储容器 SAS 令牌-输入**artifactsLocationSasToken**
   
   ![配置 Azure 文件复制任务][16]
6. 选择**Azure 资源组部署**生成步骤，并填充其值。
   
   * Azure 连接类型-选择**Azure 资源管理器**
   * Azure RM 订阅-选择用于部署中的订阅**Azure 订阅**下拉列表框。 这通常是上一步中使用的同一订阅
   * 操作-选择**创建或更新资源组**
   * 资源组-选择资源组，或输入部署新的资源组的名称
   * 位置-选择资源组的位置
   * 模板-输入的路径和要部署的模板的名称前面附加 **$ （build.stagingdirectory)**，例如： **$(Build.StagingDirectory/DSC-CI/azuredeploy.json)**
   * 模板参数-输入的路径和要使用的参数名称前面添加 **$ （build.stagingdirectory)**，例如： **$(Build.StagingDirectory/DSC-CI/azuredeploy.parameters.json)**
   * 替代模板参数-输入或复制并粘贴以下代码：
     
     ```    
     -_artifactsLocation $(artifactsLocation) -_artifactsLocationSasToken (ConvertTo-SecureString -String "$(artifactsLocationSasToken)" -AsPlainText -Force)
     ```
     ![配置 Azure 资源组部署任务][17]
7. 添加所需的所有项后，保存生成管道，并选择**使新生成入队**顶部。

## <a name="next-steps"></a>后续步骤
读取[Azure 资源管理器概述](/azure-resource-manager/resource-group-overview.md)若要了解有关 Azure 资源管理器和 Azure 资源组的详细信息。

[0]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough1.png
[1]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough2.png
[2]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough3.png
[3]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough4.png
[4]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough5.png
[5]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough6.png
[8]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough9.png
[9]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough10.png
[10]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough11b.png
[11]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough12.png
[12]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough13.png
[13]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough14.png
[14]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough15.png
[15]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough16.png
[16]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough17.png
[17]: media/vs-azure-tools-resource-groups-ci-in-vsts/walkthrough18.png
