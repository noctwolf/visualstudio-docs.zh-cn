---
title: 配置 Azure 项目使用多个服务配置 |Microsoft Docs
description: 了解如何通过更改 ServiceDefinition.csdef、 ServiceConfiguration.Local.cscfg 和 ServiceConfiguration.Cloud.cscfg 文件中配置 Azure 云服务项目。
author: ghogen
manager: douge
assetId: a4fb79ed-384f-4183-9f74-5cac257206b9
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/11/2017
ms.author: ghogen
ms.openlocfilehash: f309c2a960d011601a9fdd41e29d767c667de838
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001567"
---
# <a name="configuring-your-azure-project-in-visual-studio-to-use-multiple-service-configurations"></a>在 Visual Studio 中配置 Azure 项目以使用多个服务配置

在 Visual Studio 中的 Azure 云服务项目包括三个配置文件： `ServiceDefinition.csdef`， `ServiceConfiguration.Local.cscfg`，和`ServiceConfiguration.Cloud.cscfg`:

- `ServiceDefinition.csdef` 将部署到 Azure 来描述云服务及其角色的要求，并提供适用于所有实例的设置。 可以在运行时使用 Azure 服务托管运行时 API 读取设置。 仅当停止云服务时，可以在 Azure 上更新此文件。
- `ServiceConfiguration.Local.cscfg` 和`ServiceConfiguration.Cloud.cscfg`提供值的定义中的设置文件，并指定要为每个角色运行的实例数。 "本地"文件包含在本地调试; 中使用的值"云"文件部署到 Azure 作为`ServiceConfiguration.cscfg`并提供了有关服务器环境的设置。 在 Azure 中运行你的云服务时，可以更新此文件。

管理和在 Visual Studio 中的适用角色使用属性页中修改配置设置 (右键单击角色并选择**属性**，或双击角色)。 更改可以应用范围限定为中所选择的任何配置**服务配置**下拉列表。 Web 和辅助角色的属性是相似，不同之处的以下各节中所述。

![VS_Solution_Explorer_Roles_Properties](./media/vs-azure-tools-multiple-services-project-configurations/IC784076.png)

有关服务定义和服务配置文件的基础架构的信息，请参阅[.csdef XML 架构](/azure/cloud-services/schema-csdef-file.md)并[.cscfg XML 架构](/azure/cloud-services/schema-cscfg-file.md)文章。 有关服务配置的详细信息，请参阅[如何配置云服务](/azure/cloud-services/cloud-services-how-to-configure-portal)。


## <a name="configuration-page"></a>配置页

### <a name="service-configuration"></a>服务配置

选择一个要`ServiceConfiguration.*.cscfg`文件受影响的更改。 默认情况下，没有本地和云变体，并且可以使用**管理...** 命令复制、 重命名和删除配置文件。 这些文件添加到你的云服务项目，并显示在**解决方案资源管理器**。 但是，只能从该控件可以完成重命名或删除配置。

### <a name="instances"></a>实例数

设置**实例**属性设置为服务应为此角色运行的实例数进行计数。

设置**VM 大小**属性设置为**特小**，**小**，**中等**，**大**，或**特大规模**。  有关详细信息，请参阅[云服务大小](/azure/cloud-services/cloud-services-sizes-specs)。

### <a name="startup-action-web-role-only"></a>启动操作 （仅 Web 角色）

设置指定在开始调试时，Visual Studio 应启动 web 浏览器的 HTTP 终结点和/或 HTTPS 终结点，此属性。

**HTTPS 终结点**仅当已为你的角色定义 HTTPS 终结点选项才可用。 您可以定义 HTTPS 终结点**终结点**属性页。

如果已添加 HTTPS 终结点，默认情况下，启用 HTTPS 终结点选项，并且在开始调试，除了浏览器为 HTTP 终结点，假定这两个启动选项处于启用状态时，Visual Studio 将启动此终结点的浏览器。

### <a name="diagnostics"></a>诊断

默认情况下，Web 角色启用诊断。 Azure 云服务项目和存储帐户设置为使用本地存储仿真程序。 当准备好部署到 Azure，你可以选择生成器按钮 (**...**) 以改为使用 Azure 存储。 可以按需或按自动计划的间隔将诊断数据传输到存储帐户。 有关 Azure 诊断的详细信息，请参阅[在 Azure 云服务和虚拟机中启用诊断](/azure/cloud-services/cloud-services-dotnet-diagnostics)。

## <a name="settings-page"></a>设置页

上**设置**页上，您可以以名称-值对的形式添加到配置设置。 角色中运行的代码可以读取配置设置在运行时使用提供的类的值[Azure 托管库](http://go.microsoft.com/fwlink?LinkID=171026)，具体而言， [GetConfigurationSettingValue](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleenvironment.getconfigurationsettingvalue.aspx)方法。

### <a name="configuring-a-connection-string-for-a-storage-account"></a>配置存储帐户的连接字符串

连接字符串是存储模拟器或 Azure 存储帐户提供连接和身份验证信息的设置。 无论何时在角色中的代码访问 Azure 存储 （blob、 队列或表），它需要一个连接字符串。

> [!Note]
> Azure 存储帐户的连接字符串必须使用定义的格式 (请参阅[配置 Azure 存储连接字符串](/azure/storage/common/storage-configure-connection-string))。

您可以设置连接字符串以根据需要然后将设置为 Azure 存储帐户部署应用程序时使用本地存储的云服务。 未能正确设置连接字符串可能会导致角色无法启动，或是初始化、 忙碌、 停止状态之间循环。

若要创建连接字符串，请选择**添加设置**并设置**类型**到"连接字符串"。

对于新的或现有的连接字符串，选择 **...*** 的右侧**值**字段，打开**创建存储连接字符串**对话框：

1. 下**使用连接**，选择**你的订阅**选项可从订阅选择存储帐户。 Visual Studio 然后将获取存储帐户凭据从自动`.publishsettings`文件。
1. 选择**手动输入的凭据**允许您指定的帐户名称和密钥直接使用 Azure 门户中的信息。 若要复制帐户密钥：
    1. 导航到门户并选择 Azure 上的存储帐户**管理密钥**。
    1. 若要复制的帐户密钥，请导航到在 Azure 门户中，选择存储帐户**设置 > 访问密钥**，然后使用复制按钮将主访问密钥复制到剪贴板。
1. 选择一个连接选项。 **指定自定义终结点**会要求你指定的特定 Url 的 blob、 表和队列。 自定义终结点，可以使用[自定义域](/azure/storage/blobs/storage-custom-domain-name.md)以及更精确地控制访问。 请参阅[配置 Azure 存储连接字符串](/azure/storage/common/storage-configure-connection-string)。
1. 选择**确定**，然后**文件 > 保存**使用新的连接字符串更新配置。

同样，当您发布到 Azure 应用程序，选择包含连接字符串的 Azure 存储帐户的服务配置。 发布你的应用程序后，验证应用程序按预期方式针对 Azure 存储服务正常工作。

有关如何更新服务配置的详细信息，请参阅明[管理的存储帐户连接字符串](vs-azure-tools-configure-roles-for-cloud-service.md#manage-connection-strings-for-storage-accounts)。

## <a name="endpoints-page"></a>终结点页面

Web 角色通常在端口 80 上具有单个 HTTP 终结点。 但是，辅助角色，可以有任意数量的 HTTP、 HTTPS 或 TCP 终结点。 终结点可以是输入终结点，可供外部客户端或可供服务中运行其他角色的内部终结点。

- 若要使 HTTP 终结点可供外部客户端和 Web 浏览器，更改终结点类型的输入，并指定名称和公用端口号。
- 若要使 HTTPS 终结点可供外部客户端和 Web 浏览器中，将终结点类型更改为**输入**，并指定一个名称、 公用端口号和管理证书名称。 此外必须在定义的证书**证书**属性页，然后才能指定管理证书。 
- 若要使终结点可供内部访问云服务中的其他角色，将终结点类型更改为内部，并指定名称和可行的专用端口为此终结点。

## <a name="local-storage-page"></a>本地存储页

可以使用**本地存储**属性页保留了角色的一个或多个本地存储资源。 本地存储资源是角色的 Azure 虚拟机在其中运行实例的文件系统中的保留的目录。

## <a name="certificates-page"></a>证书页

**证书**属性页会将有关证书的信息添加到服务配置。 请注意，您的证书不会打包到与你的服务;您必须将证书单独上载到 Azure [Azure 门户](http://portal.azure.com)。

添加证书将有关证书的信息添加到你的服务配置。 证书与服务; 不会一起打包您必须单独通过 Azure 门户将证书上传。

若要将证书与角色相关联，请提供证书的名称。 此名称用于引用证书上配置 HTTPS 终结点时**终结点**页。 接下来，指定的证书存储区是否**本地计算机**或**当前用户**和存储的名称。 最后，输入证书的指纹。 如果证书是在当前用户 \ 个人 （我的） 存储，可以通过从填充列表中选择证书来输入证书的指纹。 如果驻留在其他位置，请手动输入指纹值。

当您从证书存储区添加证书时，任何中间证书会自动添加到你的配置设置。 此外，必须将这些中间证书上载到 Azure 来正确配置服务的 SSL。

只有在云中运行时，你将与你的服务相关联的所有管理证书都应用到该服务。 当在本地开发环境中运行你的服务时，它使用由计算模拟器管理的标准证书。
