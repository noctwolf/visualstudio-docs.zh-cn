---
title: 使用 Visual Studio 配置 Azure 云服务的角色 |Microsoft Docs
description: 了解如何设置和配置为使用 Visual Studio 的 Azure 云服务角色。
author: ghogen
manager: douge
assetId: d397ef87-64e5-401a-aad5-7f83f1022e16
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/21/2017
ms.author: ghogen
ms.openlocfilehash: ce2259debb55c4792c2998f0e67df69dbc8cb7f9
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001596"
---
# <a name="configure-azure-cloud-service-roles-with-visual-studio"></a>使用 Visual Studio 配置 Azure 云服务角色
Azure 云服务可以有一个或多个辅助角色或 web 角色。 对于每个角色，您需要定义该角色的设置方式，并配置该角色的运行方式。 若要了解有关云服务中的角色的详细信息，请观看视频[介绍了 Azure 云服务](https://channel9.msdn.com/Series/Windows-Azure-Cloud-Services-Tutorials/Introduction-to-Windows-Azure-Cloud-Services)。 

你的云服务的信息存储在以下文件：

- **ServiceDefinition.csdef** -服务定义文件定义运行时设置，包括所需角色的云服务、 终结点和虚拟机大小。 None 中存储的数据`ServiceDefinition.csdef`角色正在运行时，可以更改。
- **ServiceConfiguration.cscfg** -服务配置文件配置运行角色的多少个实例，并为角色定义的设置值。 中存储的数据`ServiceConfiguration.cscfg`运行你的角色时，可以更改。

若要存储控制角色的运行方式的设置不同的值，可以定义多个服务配置。 可以为每个部署环境使用不同的服务配置。 例如，可以设置存储帐户连接字符串以使用本地 Azure 存储模拟器在本地服务配置并创建另一个服务配置为在云中使用 Azure 存储。

在 Visual Studio 中创建 Azure 云服务时，两个服务配置自动创建并添加到 Azure 项目：

- `ServiceConfiguration.Cloud.cscfg`
- `ServiceConfiguration.Local.cscfg`

## <a name="configure-an-azure-cloud-service"></a>配置 Azure 云服务
可以在 Visual Studio 中，配置 Azure 云服务从解决方案资源管理器，如以下步骤中所示：

1. 创建或在 Visual Studio 中打开 Azure 云服务项目。

1. 在中**解决方案资源管理器**，右键单击项目，并从上下文菜单中，选择**属性**。
   
    ![解决方案资源管理器项目上下文菜单](./media/vs-azure-tools-configure-roles-for-cloud-service/solution-explorer-project-context-menu.png)

1. 在项目的属性页中，选择**开发**选项卡。 

    ![项目属性页-开发选项卡](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-development-tab.png)

1. 在中**服务配置**列表中，选择你想要编辑的服务配置的名称。 (如果你想要对此角色的所有服务配置进行更改，请选择**所有配置**。)
   
    > [!IMPORTANT]
    > 如果您选择特定服务配置，某些属性被禁用，因为它们仅设置为所有配置。 若要编辑这些属性，必须选择**所有配置**。
    > 
    > 
   
    ![Azure 云服务的服务配置列表](./media/vs-azure-tools-configure-roles-for-cloud-service/cloud-service-service-configuration-property.png)

## <a name="change-the-number-of-role-instances"></a>更改角色实例数
若要提高你的云服务的性能，可以更改正在运行，根据用户或预期负载的特定角色的数量的角色实例数。 在 Azure 中运行云服务时，将为每个角色实例创建单独的虚拟机。 这会影响部署此云服务的计费。 有关计费的详细信息，请参阅[了解你的 Microsoft Azure 帐单](/azure/billing/billing-understand-your-bill)。

1. 创建或在 Visual Studio 中打开 Azure 云服务项目。

1. 在中**解决方案资源管理器**，展开项目节点。 下**角色**节点，右键单击你想要更新，并从上下文菜单中，选择的角色**属性**。

    ![解决方案资源管理器 Azure 角色上下文菜单](./media/vs-azure-tools-configure-roles-for-cloud-service/solution-explorer-azure-role-context-menu.png)

1. 选择**配置**选项卡。

    ![配置选项卡](./media/vs-azure-tools-configure-roles-for-cloud-service/role-configuration-properties-page.png)

1. 在中**服务配置**列表中，选择你想要更新的服务配置。
   
    ![服务配置列表](./media/vs-azure-tools-configure-roles-for-cloud-service/role-configuration-properties-page-select-configuration.png)

1. 在中**实例计数**文字框中，输入想要启动此角色的实例数。 当您发布到 Azure 云服务时，每个实例在单独的虚拟机上运行。

    ![正在更新实例计数](./media/vs-azure-tools-configure-roles-for-cloud-service/role-configuration-properties-page-instance-count.png)

1. 从 Visual Studio 工具栏中，选择**保存**。

## <a name="manage-connection-strings-for-storage-accounts"></a>管理存储帐户的连接字符串
您可以添加、 删除或修改服务配置的连接字符串。 例如，可能想本地连接字符串，值为本地服务配置`UseDevelopmentStorage=true`。 您可能想要配置在 Azure 中使用的存储帐户的云服务配置。

> [!WARNING]
> 当输入存储帐户连接字符串的 Azure 存储帐户密钥信息时，此信息存储在本地服务配置文件中。 但是，此信息当前未存储为加密的文本。
> 
> 

通过每个服务配置使用不同的值，无需在你的云服务中使用不同的连接字符串或修改你的代码时将你的云服务发布到 Azure。 可以在代码中使用连接字符串的相同名称和值会不同，基于或将其发布时生成你的云服务选择的服务配置。

1. 创建或在 Visual Studio 中打开 Azure 云服务项目。

1. 在中**解决方案资源管理器**，展开项目节点。 下**角色**节点，右键单击你想要更新，并从上下文菜单中，选择的角色**属性**。

    ![解决方案资源管理器 Azure 角色上下文菜单](./media/vs-azure-tools-configure-roles-for-cloud-service/solution-explorer-azure-role-context-menu.png)

1. 选择**设置**选项卡。

    ![设置选项卡](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab.png)

1. 在中**服务配置**列表中，选择你想要更新的服务配置。

    ![服务配置](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab-select-configuration.png)

1. 若要添加连接字符串，请选择**添加设置**。

    ![添加连接字符串](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab-add-setting.png)

1. 新设置添加到列表后，请使用所需的信息更新列表中的行。

    ![新的连接字符串](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab-add-setting-new-setting.png)

    - **名称**-输入想要使用的连接字符串的名称。
    - **类型**-选择**连接字符串**从下拉列表。
    - **值**-你可以输入连接字符串直接插入**值**单元格，或选择省略号 （...） 以在工作**创建存储连接字符串**对话框。  

1. 在中**创建存储连接字符串**对话框中，选择一个选项**连接使用**。 然后按照所选择的选项的说明：

    - **Microsoft Azure 存储模拟器**-如果选择此选项，在对话框中的剩余设置被禁用，因为它们仅适用于 Azure。 选择“确定”。
    - **你的订阅**-如果选择此选项，使用下拉列表中选择并登录到 Microsoft 帐户，或添加 Microsoft 帐户。 选择 Azure 订阅和存储帐户。 选择“确定”。
    - **手动输入的凭据**-输入存储帐户名称和主密钥或第二个密钥。 选择一个选项来**连接**（建议使用 HTTPS 在大多数情况下。）选择“确定”。

1. 若要删除的连接字符串，选择连接字符串，然后选择**删除设置**。

1. 从 Visual Studio 工具栏中，选择**保存**。

## <a name="programmatically-access-a-connection-string"></a>以编程方式访问连接字符串

以下步骤演示如何以编程方式访问连接字符串使用C#。

1. 添加以下 using 指令C#文件要使用的设置：

    ```csharp
    using Microsoft.WindowsAzure;
    using Microsoft.WindowsAzure.Storage;
    using Microsoft.WindowsAzure.ServiceRuntime;
    ```

1. 下面的代码演示了如何访问连接字符串的示例。 替换为&lt;ConnectionStringName > 占位符替换相应的值。 

    ```csharp
    // Setup the connection to Azure Storage
    var storageAccount = CloudStorageAccount.Parse(RoleEnvironment.GetConfigurationSettingValue("<ConnectionStringName>"));
    ```

## <a name="add-custom-settings-to-use-in-your-azure-cloud-service"></a>添加要在 Azure 云服务中使用的自定义设置
服务配置文件中的自定义设置，可以添加一个名称和特定服务配置的字符串值。 您可以选择使用此设置来配置你的云服务中的功能，通过读取设置的值，并使用此值来控制在代码中的逻辑。 而无需重新生成服务包或运行你的云服务时，可以更改这些服务配置值。 你的代码可以检查通知的设置发生更改时。 请参阅[RoleEnvironment.Changing 事件](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleenvironment.changing.aspx)。

您可以添加、 删除或修改服务配置的自定义设置。 这些字符串的不同服务配置的可能需要不同的值。

通过每个服务配置使用不同的值，无需在你的云服务中使用不同的字符串或修改你的代码时将你的云服务发布到 Azure。 可以在代码中使用字符串的相同名称和值会不同，基于或将其发布时生成你的云服务选择的服务配置。

1. 创建或在 Visual Studio 中打开 Azure 云服务项目。

1. 在中**解决方案资源管理器**，展开项目节点。 下**角色**节点，右键单击你想要更新，并从上下文菜单中，选择的角色**属性**。

    ![解决方案资源管理器 Azure 角色上下文菜单](./media/vs-azure-tools-configure-roles-for-cloud-service/solution-explorer-azure-role-context-menu.png)

1. 选择**设置**选项卡。

    ![设置选项卡](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab.png)

1. 在中**服务配置**列表中，选择你想要更新的服务配置。

    ![服务配置列表](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab-select-configuration.png)

1. 若要添加自定义设置，请选择**添加设置**。

    ![添加自定义设置](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab-add-setting.png)

1. 新设置添加到列表后，请使用所需的信息更新列表中的行。

    ![新的自定义设置](./media/vs-azure-tools-configure-roles-for-cloud-service/project-properties-settings-tab-add-setting-new-setting.png)

    - **名称**-输入设置的名称。
    - **类型**-选择**字符串**从下拉列表。
    - **值**-输入设置的值。 您可以输入的值直接插入**值**单元格，或选择省略号 （...） 以输入值**编辑字符串**对话框。  

1. 要删除自定义设置，请选择该设置，并选择**删除设置**。

1. 从 Visual Studio 工具栏中，选择**保存**。

## <a name="programmatically-access-a-custom-settings-value"></a>以编程方式访问自定义设置的值
 
以下步骤演示如何以编程方式访问自定义设置使用C#。

1. 添加以下 using 指令C#文件要使用的设置：

    ```csharp
    using Microsoft.WindowsAzure;
    using Microsoft.WindowsAzure.Storage;
    using Microsoft.WindowsAzure.ServiceRuntime;
    ```

1. 下面的代码演示了如何访问自定义设置的示例。 替换为&lt;SettingName > 占位符替换相应的值。 
    
    ```csharp
    var settingValue = RoleEnvironment.GetConfigurationSettingValue("<SettingName>");
    ```

## <a name="manage-local-storage-for-each-role-instance"></a>管理每个角色实例的本地存储
您可以添加为每个角色实例的本地文件系统存储。 通过为该数据存储中，角色的其他实例或其他角色存储，存储不可访问的数据。  

1. 创建或在 Visual Studio 中打开 Azure 云服务项目。

1. 在中**解决方案资源管理器**，展开项目节点。 下**角色**节点，右键单击你想要更新，并从上下文菜单中，选择的角色**属性**。

    ![解决方案资源管理器 Azure 角色上下文菜单](./media/vs-azure-tools-configure-roles-for-cloud-service/solution-explorer-azure-role-context-menu.png)

1. 选择**本地存储**选项卡。

    ![本地存储选项卡](./media/vs-azure-tools-configure-roles-for-cloud-service/role-local-storage-tab.png)

1. 在中**服务配置**列表中，确保**所有配置**所选为本地存储设置适用于所有服务配置。 任何其他值会导致禁用页面上的所有输入字段。 

    ![服务配置列表](./media/vs-azure-tools-configure-roles-for-cloud-service/role-local-storage-tab-service-configuration.png)

1. 若要添加本地存储条目，请选择**添加本地存储**。

    ![添加本地存储](./media/vs-azure-tools-configure-roles-for-cloud-service/role-local-storage-tab-add-local-storage.png)

1. 新的本地存储条目添加到列表后，使用所需的信息更新列表中的行。

    ![新的本地存储项](./media/vs-azure-tools-configure-roles-for-cloud-service/role-local-storage-tab-new-local-storage.png)

    - **名称**-输入想要用于新本地存储的名称。
    - **大小 (MB)** -以 mb 为单位的所需的新本地存储输入的大小。
    - **清理在角色回收**-选择此选项可在新的本地存储中删除数据，角色的虚拟机回收时。

1. 若要删除本地存储条目，选择该条目，然后选择**删除本地存储**。

1. 从 Visual Studio 工具栏中，选择**保存**。

## <a name="programmatically-accessing-local-storage"></a>以编程方式访问本地存储

本部分演示了如何以编程方式访问本地存储使用C#通过编写测试文本文件`MyLocalStorageTest.txt`。  

### <a name="write-a-text-file-to-local-storage"></a>文本文件写入本地存储

下面的代码演示如何将文本文件写入本地存储的示例。 替换为&lt;LocalStorageName > 占位符替换相应的值。 

    ```csharp
    // Retrieve an object that points to the local storage resource
    LocalResource localResource = RoleEnvironment.GetLocalResource("<LocalStorageName>");
    
    //Define the file name and path
    string[] paths = { localResource.RootPath, "MyLocalStorageTest.txt" };
    String filePath = Path.Combine(paths);
    
    using (FileStream writeStream = File.Create(filePath))
    {
        Byte[] textToWrite = new UTF8Encoding(true).GetBytes("Testing Web role storage");
        writeStream.Write(textToWrite, 0, textToWrite.Length);
    }

    ```

### <a name="find-a-file-written-to-local-storage"></a>查找文件写入到本地存储

若要查看上一节中的代码创建的文件，请执行以下步骤：
    
1.  在 Windows 通知区域中，右键单击 Azure 图标，并从上下文菜单中，选择**显示计算模拟器 UI**。 

    ![显示 Azure 计算仿真程序](./media/vs-azure-tools-configure-roles-for-cloud-service/show-compute-emulator.png)

1. 选择 web 角色。

    ![Azure 计算仿真程序](./media/vs-azure-tools-configure-roles-for-cloud-service/compute-emulator.png)

1. 上**Microsoft Azure 计算模拟器**菜单中，选择**工具** > **打开本地存储**。

    ![打开本地存储菜单项](./media/vs-azure-tools-configure-roles-for-cloud-service/compute-emulator-open-local-store-menu.png)

1. Windows 资源管理器窗口打开时，输入 MyLocalStorageTest.txt 到**搜索**文本框中，然后选择**Enter**开始搜索。 

## <a name="next-steps"></a>后续步骤
通过阅读了解有关 Visual Studio 中的 Azure 项目的详细信息[配置 Azure 项目](vs-azure-tools-configuring-an-azure-project.md)。 通过阅读了解有关云服务架构的详细信息[架构参考](https://msdn.microsoft.com/library/azure/dd179398)。

