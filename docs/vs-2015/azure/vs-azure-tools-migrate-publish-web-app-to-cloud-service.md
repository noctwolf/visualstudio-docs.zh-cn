---
title: 如何迁移和发布到 Azure 云服务的 Web 应用程序从 Visual Studio |Microsoft Docs
description: 了解如何迁移和通过使用 Visual Studio 发布到 Azure 云服务 web 应用程序
author: ghogen
manager: douge
ms.assetid: 9394adfd-a645-4664-9354-dd5df08e8c91
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 11/10/2017
ms.author: ghogen
ms.openlocfilehash: c122b54a4e22285678d13213cc73d6492baba629
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001589"
---
# <a name="how-to-migrate-and-publish-a-web-application-to-an-azure-cloud-service-from-visual-studio"></a>如何： 迁移和发布到 Azure 云服务的 Web 应用程序从 Visual Studio

若要充分利用托管服务和 Azure 的缩放功能，您可能想要迁移并将其部署到 Azure 云服务 web 应用程序。 最小的更改是必需的。 本文介绍了如何部署到仅限; 云服务应用服务中，请参阅[部署 Azure 应用服务中的 web 应用](/azure/app-service/app-service-deploy-local-git)。

> [!Important]
> 仅对特定的 ASP.NET、 Silverlight、 WCF 和 WCF 工作流项目支持这种迁移。 不支持 ASP.NET Core 项目。 请参阅[支持的项目模板](#supported-project-templates)。

## <a name="migrate-a-project-to-cloud-services"></a>将项目迁移到云服务

1. 右键单击 web 应用程序项目并选择**转换 > 转换为 Microsoft Azure 云服务项目**。 （请注意，是否解决方案中已有 web 角色项目，此命令不会显示。）
1. Visual Studio 的解决方案中的包含所需的 web 角色创建云服务项目。 此项目的名称是相同作为你的应用程序项目加上后缀`.Azure`。
1. Visual Studio 还将设置**Copy Local**属性设为 true 的 MVC 2 中，MVC 3 中，MVC 4 和 Silverlight 业务应用程序所需的任何程序集。 此属性将这些程序集添加到用于部署的服务包。

   > [!Important]
   > 如果你有其他程序集或文件所需的此 web 应用程序，必须手动设置这些文件的属性。 有关如何设置这些属性的信息，请参阅[在服务包中包含文件](#include-files-in-the-service-package)。

### <a name="errors-and-warnings"></a>错误和警告

任何警告或发生的错误指示要部署到 Azure，例如缺少程序集之前解决的问题。

如果生成应用程序、 使用计算模拟器本地运行或将其发布到 Azure 时，可能会看到错误:"指定的路径、 文件名，或两者都太长。" 此错误表示完全限定的 Azure 项目名称的长度超过了 146 个字符。 若要更正此问题，请将你的解决方案移到路径较短的不同文件夹。

有关如何将任何警告视为错误的详细信息，请参阅[使用 Visual Studio 配置 Azure 云服务项目](vs-azure-tools-configuring-an-azure-project.md)。

### <a name="test-the-migration-locally"></a>在本地测试迁移

1. 在 Visual Studio**解决方案资源管理器**，右键单击添加的云服务项目并选择**设为启动项目**。
1. 选择**调试 > 启动调试**(F5) 以启动 Azure 调试环境。 此环境专门提供了各种 Azure 服务的模拟。

### <a name="use-an-azure-sql-database-for-your-application"></a>为应用程序使用 Azure SQL 数据库

如果必须为 web 应用程序使用的本地 SQL Server 数据库的连接字符串，必须将数据库迁移到 Azure SQL 数据库，并更新你的连接字符串。 有关此过程的指导，请参阅以下主题：

- [SQL Server 数据库迁移到云中的 SQL 数据库](/azure/sql-database/sql-database-cloud-migrate)
- [使用.NET (C#) 与 Visual Studio 进行连接和查询和 Azure SQL 数据库](/azure/sql-database/sql-database-connect-query-dotnet-visual-studio)。

## <a name="publish-the-application-to-azure-cloud-service"></a>发布到 Azure 云服务应用程序

1. 创建必需的云服务和存储帐户在 Azure 订阅中所描述的方法[准备发布或部署 Azure 应用程序从 Visual Studio](vs-azure-tools-cloud-service-publish-set-up-required-services-in-visual-studio.md)。
1. 在 Visual Studio 中，右键单击应用程序项目并选择**发布到 Microsoft Azure...** （即与"发布..."命令不同。）。
1. 在中**发布 Azure 应用程序**出现，在使用具有 Azure 订阅的帐户登录，并选择**下一步 >**。
1. 在中**设置 > 通用设置**选项卡上，选择的目标云服务**云服务**下拉列表中，以及选定的环境和配置。 
1. 在中**设置 > 高级设置**，选择要使用，然后选择存储帐户**下一步 >**。
1. 在中**诊断**，选择是否要将信息发送到 Application Insights。
1. 选择**下一步 >** 若要查看摘要，然后选择**发布**以启动部署。
1. Visual Studio 将打开活动日志窗口，您可以在其中跟踪进度：

    ![VST_AzureActivityLog](./media/vs-azure-tools-migrate-publish-web-app-to-cloud-service/IC744149.png)

1. （可选）若要取消部署过程，请右键单击活动日志中的行项目，然后选择**取消并删除**。 此命令会停止部署过程，并从 Azure 中删除部署环境。 注意： 若要完成部署后，请删除此部署环境，你必须使用[Azure 门户](https://portal.azure.com)。
1. （可选）角色实例启动后，Visual Studio 将自动显示部署环境**服务器资源管理器 > 云服务**节点。 从此处可以查看单个角色实例的状态。
1. 若要访问你的应用程序部署后，选择你的部署时的状态旁边的箭头**Completed**将出现在**Azure 活动日志**以及的 URL。 请参阅下表，了解有关如何从 Azure 启动特定类型的 web 应用程序的详细信息。

## <a name="using-the-compute-emulator-and-starting-application-in-azure"></a>使用计算仿真程序并在 Azure 中启动应用程序

可以在浏览器通过选择连接到 Visual Studio 调试器中启动所有应用程序类型**调试 > 启动调试**(F5)。 使用 ASP.NET 空 Web 应用程序项目，首先必须添加`.aspx`中你的应用程序页上，并将其设置为你的 web 项目的起始页。

下表提供了有关在 Azure 中启动应用程序的详细信息：

   | Web 应用程序类型 | 在 Azure 中运行 |
   | --- | --- | --- |
   | ASP.NET Web 应用程序<br/>（包括 MVC 2，MVC 3，MVC 4） | 选择中的 URL**部署**选项卡上的**Azure 活动日志**。 |
   | ASP.NET 空 Web 应用程序 | 如果有默认值`.aspx`在你的应用程序页上，选择中的 URL**部署**选项卡上的**Azure 活动日志**。 若要导航到其他页面，请在浏览器中输入以下格式的 URL: `<deployment_url>/<page_name>.aspx` |
   | Silverlight 应用程序<br/>Silverlight 业务应用程序<br/>Silverlight 导航应用程序 | 导航到应用程序中使用以下 URL 窗体的特定页： `<deployment_url>/<page_name>.aspx` |
    WCF 服务应用程序<br/>WCF 工作流服务应用程序 | 设置`.svc`WCF 服务项目的起始页文件。 然后导航到 `<deployment_url>/<service_file>.svc` |
   | ASP.NET 动态实体<br/>ASP.NET 动态数据 Linq to SQL | 下一节中所述的更新的连接字符串。 然后导航到`<deployment_url>/<page_name>.aspx`。 对于 Linq to SQL 中，必须使用 Azure SQL 数据库。 |

## <a name="update-a-connection-string-for-aspnet-dynamic-entities"></a>为 ASP.NET 动态实体更新连接字符串

1. 创建用于 ASP.NET Dynamic Entities web 应用程序的 SQL Azure 数据库 (#use-an-azuresql-database-for-your-application) 中所述。
1. 添加表和此数据库从 Azure 门户所需的字段。
1. 指定连接字符串中的`web.config`文件具有以下格式，并保存该文件：

    ```xml
    <addname="tempdbEntities"connectionString="metadata=res://*/Model1.csdl|res://*/Model1.ssdl|res://*/Model1.msl;provider=System.Data.SqlClient;provider connection string=&quot;data source=<server name>\SQLEXPRESS;initial catalog=<database name>;integrated security=True;multipleactiveresultsets=True;App=EntityFramework&quot;"providerName="System.Data.EntityClient"/>
    ```

    更新*connectionString*值与 SQL Azure 数据库的 ADO.NET 连接字符串，如下所示：

    ```xml
    XMLCopy<addname="tempdbEntities"connectionString="metadata=res://*/Model1.csdl|res://*/Model1.ssdl|res://*/Model1.msl;provider=System.Data.SqlClient;provider connection string=&quot;Server=tcp:<SQL Azure server name>.database.windows.net,1433;Database=<database name>;User ID=<user name>;Password=<password>;Trusted_Connection=False;Encrypt=True;multipleactiveresultsets=True;App=EntityFramework&quot;"providerName="System.Data.EntityClient"/>
    ```

## <a name="supported-project-templates"></a>支持的项目模板

可迁移和发布到云服务应用程序必须在下表中使用的模板之一。 不支持 ASP.NET Core。

| 模板组 | 项目模板 |
| --- | --- |
| Web | ASP.NET Web 应用程序 (.NET Framework) |
| Web | ASP.NET MVC 2 Web 应用程序 |
| Web | ASP.NET MVC 3 Web 应用程序 |
| Web | ASP.NET MVC4 Web 应用程序 |
| Web | ASP.NET 空 Web 应用程序 （或站点） |
| Web | ASP.NET MVC 2 空 Web 应用程序 |
| Web | ASP.NET Dynamic Data 实体 Web 应用程序 |
| Web | ASP.NET 动态数据 Linq to SQL Web 应用程序 |
| Silverlight | Silverlight 应用程序 |
| Silverlight | Silverlight 业务应用程序 |
| Silverlight | Silverlight 导航应用程序 |
| WCF | WCF 服务应用程序 |
| WCF | WCF 工作流服务应用程序 |
| 工作流 | WCF 工作流服务应用程序 |

## <a name="next-steps"></a>后续步骤

- [准备发布或部署 Azure 应用程序从 Visual Studio](vs-azure-tools-cloud-service-publish-set-up-required-services-in-visual-studio.md)
- [设置命名的身份验证凭据](vs-azure-tools-setting-up-named-authentication-credentials.md)。
