---
title: 为 Azure 云服务和虚拟机设置诊断 |Microsoft Docs
description: 了解如何设置用于调试 Azure 云服务和虚拟机 (Vm) 在 Visual Studio 中的诊断。
author: mikejo5000
manager: douge
ms.assetid: e70cd7b4-6298-43aa-adea-6fd618414c26
ms.topic: conceptual
ms.workload: azure-vs
ms.date: 06/28/2018
ms.author: mikejo
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.openlocfilehash: 4448825c5d443887833a405aab14d2243a0e5216
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001595"
---
# <a name="set-up-diagnostics-for-azure-cloud-services-and-virtual-machines"></a>为 Azure 云服务和虚拟机设置诊断
当需要对 Azure 云服务或虚拟机进行故障排除时，可以使用 Visual Studio 更轻松地设置 Azure 诊断。 诊断捕获系统数据和日志记录数据的虚拟机和运行云服务的虚拟机实例上。 诊断数据传输到您选择的存储帐户。 有关诊断的详细信息记录在 Azure 中，请参阅[启用 Azure 应用服务中的 Web 应用的诊断日志记录](/azure/app-service/web-sites-enable-diagnostic-log)。

在本文中，我们演示您如何使用 Visual Studio 来打开和前和部署后设置 Azure 诊断。 了解如何在 Azure 虚拟机上设置诊断、 如何选择类型的诊断信息收集，以及如何查看收集的信息。

可以使用以下选项之一来设置 Azure 诊断：

* 中更改诊断设置**诊断配置**Visual Studio 中的对话框。 设置保存在名为 diagnostics.wadcfgx （在 Azure SDK 2.4 及更早版本，该文件被称为 diagnostics.wadcfg） 的文件。 您还可以直接修改配置文件。 如果手动更新文件，此配置更改生效下, 一次部署云服务到 Azure，或在模拟器中运行该服务。
* 使用云资源管理器或 Visual Studio 中的服务器资源管理器更改为云服务或正在运行的虚拟机的诊断设置。

## <a name="azure-sdk-26-diagnostics-changes"></a>Azure SDK 2.6 诊断更改
以下更改适用于 Azure SDK 2.6 和更高版本在 Visual Studio 中的项目：

* 本地模拟器现在支持诊断。 这意味着您可以收集诊断数据并确保在开发和测试 Visual Studio 中时，你的应用程序，创建相应的跟踪。 连接字符串`UseDevelopmentStorage=true`通过使用 Azure 存储模拟器在 Visual Studio 中运行云服务项目时启用诊断数据收集。 所有诊断数据都收集在开发存储存储帐户中。
* 诊断存储帐户连接字符串`Microsoft.WindowsAzure.Plugins.Diagnostics.ConnectionString`存储在服务配置 (.cscfg) 文件中。 在 Azure SDK 2.5 中，在 diagnostics.wadcfgx 文件中指定诊断存储帐户。

连接字符串的工作方式在 Azure SDK 2.6 和更高版本与 Azure SDK 2.4 及更早版本的某些关键方面：

* 在 Azure SDK 2.4 及更早版本，连接字符串作为用于运行时由诊断插件获取用于传输诊断日志的存储帐户信息。
* 在 Azure SDK 2.6 及更高版本，Visual Studio 使用诊断连接字符串来设置 Azure 诊断扩展使用适当的存储帐户信息在发布过程。 可以使用连接字符串来定义不同的存储帐户的 Visual Studio 在发布期间使用的不同服务配置。 但是，因为诊断插件在 Azure SDK 2.5 之后不可用，.cscfg 文件本身不能设置诊断扩展。 您必须设置扩展分别通过使用 Visual Studio 或 PowerShell 等工具。
* 为了简化使用 PowerShell 设置诊断扩展的过程，Visual Studio 的包输出包括适用于每个角色的诊断扩展的公共配置 XML。 Visual Studio 使用诊断连接字符串来填充公共配置中的存储帐户信息。 扩展文件夹中创建公共配置文件。 公共配置文件使用的命名模式 PaaSDiagnostics。&lt;角色名称\>。PubConfig.xml。 任何基于 PowerShell 的部署可以使用此模式将每个配置映射到角色。
* [Azure 门户](http://go.microsoft.com/fwlink/p/?LinkID=525040).cscfg 文件中使用的连接字符串来访问诊断数据。 数据显示在**监视**选项卡。所需的连接字符串才能设置服务后，若要在门户中显示详细监视数据。

## <a name="migrate-projects-to-azure-sdk-26-and-later"></a>迁移到 Azure SDK 2.6 及更高版本的项目
迁移时从 Azure SDK 2.5 到 Azure SDK 2.6 或更高版本，如果你有在.wadcfgx 文件中指定诊断存储帐户，存储帐户保留在该文件中。 若要利用对不同存储配置使用不同的存储帐户的灵活性，手动将连接字符串添加到你的项目。 如果要从 Azure SDK 2.4 或到 Azure SDK 2.6 之前进行迁移项目，将保留诊断连接字符串。 但请注意如何在上一部分中所述的 Azure SDK 2.6 中处理连接字符串中的更改。

### <a name="how-visual-studio-determines-the-diagnostics-storage-account"></a>Visual Studio 如何确定诊断存储帐户
* 如果在.cscfg 文件中指定了诊断连接字符串，Visual Studio 将使用它来设置诊断扩展，在发布时以及在打包过程生成公共配置 XML 文件时。
* 如果在.cscfg 文件中未指定了诊断连接字符串，Visual Studio 将回退使用.wadcfgx 文件来设置诊断扩展来发布和生成公共配置 XML 中指定的存储帐户在打包期间的文件。
* .Cscfg 文件中的诊断连接字符串将优先于.wadcfgx 文件中的存储帐户。 如果诊断连接字符串指定在.cscfg 文件中，Visual Studio 使用该连接字符串并忽略.wadcfgx 中的存储帐户。

### <a name="what-does-the-update-development-storage-connection-strings-check-box-do"></a>"更新开发存储连接字符串..."复选框的作用是什么？
**诊断和缓存的使用 Microsoft Azure 存储帐户凭据更新开发存储连接字符串，发布到 Microsoft Azure 时**复选框是方便地更新任何开发存储使用发布过程中指定的 Azure 存储帐户的帐户连接字符串。

例如，如果选择此复选框和诊断连接字符串指定`UseDevelopmentStorage=true`，当将项目发布到 Azure，Visual Studio 会自动更新诊断连接字符串中指定的存储帐户发布向导。 但是，如果实际的存储帐户指定为诊断连接字符串，该帐户是改为使用。

## <a name="diagnostics-functionality-differences-in-azure-sdk-24-and-earlier-vs-azure-sdk-25-and-later"></a>在 Azure SDK 2.4 及更低版本中的诊断功能差异。Azure SDK 2.5 及更高版本
如果要升级您的项目从 Azure SDK 2.4 和前面到 Azure SDK 2.5 或更高版本，请记住以下诊断功能差异：

* **配置 Api 已弃用**。 以编程方式配置诊断可用在 Azure SDK 2.4 及更低版本，但在 Azure SDK 2.5 及更高版本已弃用。 如果诊断配置当前在代码中定义，必须重新配置这些设置从零开始诊断已迁移的项目中继续工作。 Azure SDK 2.4 的诊断配置文件是 diagnostics.wadcfg。 Azure SDK 2.5 及更高版本的诊断配置文件是 diagnostics.wadcfgx。
* **可以仅在角色级别配置云服务应用程序的诊断**。 在 Azure SDK 2.5 及更高版本，您不能在实例级别设置云服务应用程序的诊断。
* **每次部署应用时，都会更新诊断配置**。 如果从 Visual Studio 服务器资源管理器更改诊断配置并重新部署您的应用程序，这会导致奇偶校验问题。
* **在 Azure SDK 2.5 及更高版本，在诊断配置文件中，而非代码中配置故障转储**。 如果必须在代码中配置的故障转储，你必须手动配置将从代码传输到配置文件。 故障转储并未在迁移期间传输至 Azure SDK 2.6。

## <a name="turn-on-diagnostics-in-cloud-service-projects-before-you-deploy-them"></a>部署之前对其启用云服务项目中的诊断
在 Visual Studio 中，可以收集在部署前在模拟器中运行该服务在 Azure 中运行的角色的诊断数据。 对 Visual Studio 中的诊断设置的所有更改都保存在 diagnostics.wadcfgx 配置文件。 这些设置指定在将你的云服务时保存诊断数据的存储帐户。

[!INCLUDE [cloud-services-wad-warning](./includes/cloud-services-wad-warning.md)]

### <a name="to-turn-on-diagnostics-in-visual-studio-before-deployment"></a>若要启用部署前在 Visual Studio 中的诊断

1. 在该角色的快捷菜单，选择**属性**。 在该角色的**属性**对话框中，选择**配置**选项卡。
2. 在中**诊断**部分中，请确保**启用诊断**复选框处于选中状态。
   
    ![访问启用诊断选项](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796660.png)
3. 若要指定诊断数据的存储帐户，请选择省略号 （...） 按钮。
   
    ![指定要使用的存储帐户](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796661.png)
4. 在中**创建存储连接字符串**对话框框中，指定是否想要使用 Azure 存储模拟器，Azure 订阅，连接或手动输入的凭据。
   
    ![存储帐户对话框](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796662.png)
   
   * 如果选择**Microsoft Azure 存储模拟器**，连接字符串设置为`UseDevelopmentStorage=true`。
   * 如果选择**你的订阅**，可以选择所需的 Azure 订阅，并输入帐户名称。 若要管理你的 Azure 订阅，请选择**管理帐户**。
   * 如果选择**手动输入的凭据**，输入名称和你想要使用的 Azure 帐户的密钥。
5. 若要查看**诊断配置**对话框中，选择**配置**。 除**常规**并**日志目录**，每个选项卡表示可以收集的诊断数据源。 默认值**常规**选项卡提供以下诊断数据收集选项：**仅限错误**，**的所有信息**，和**自定义计划**. 默认值**仅限错误**选项使用的存储，最少，因为它不传输警告或跟踪消息。 **的所有信息**选项传输的信息、 使用多的存储，并因此是成本最高的选项。

   > [!NOTE]
   > 有关"磁盘配额中 MB"支持的最小大小为 4 GB。 但是，如果您正在收集内存转储，此限制提高为 10 GB 之类的较高值。
   >
  
    ![启用 Azure 诊断和配置](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC758144.png)
6. 对于此示例中，选择**自定义计划**选项，以便你可以自定义收集的数据。
7. 在中**以 mb 为单位的磁盘配额**框中，您可以设置要在您为诊断数据的存储帐户中分配的空间量。 可以更改或接受默认值。
8. 在你想要收集的诊断数据的每个选项卡上，选择**启用的传输\<日志类型\>** 复选框。 例如，如果你想要收集的应用程序日志**应用程序日志**选项卡上，选择**启用应用程序日志的传输**复选框。 此外，指定每个诊断数据类型所需的任何其他信息。 每个选项卡的配置信息，请参阅的部分**设置诊断数据源**这篇文章中更高版本。 
9. 启用了所需的所有诊断数据收集后，选择**确定**。
10. 照常在 Visual Studio 中运行你的 Azure 云服务项目。 使用你的应用程序时，你已启用的日志信息保存到您指定的 Azure 存储帐户。

## <a name="turn-on-diagnostics-on-azure-virtual-machines"></a>Azure 虚拟机上启用诊断
在 Visual Studio 中，可以收集 Azure 虚拟机的诊断数据。

### <a name="to-turn-on-diagnostics-on-azure-virtual-machines"></a>若要启用 Azure 虚拟机上的诊断

1. 在服务器资源管理器，选择 Azure 节点，然后连接到你的 Azure 订阅，如果你尚未连接。
2. 展开**虚拟机**节点。 您可以创建新的虚拟机，或选择现有节点。
3. 在您想的虚拟机的快捷菜单，选择**配置**。 将显示虚拟机配置对话框。
   
    ![配置 Azure 虚拟机](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796663.png)
4. 如果尚未安装，添加 Microsoft 监视代理诊断扩展。 使用此扩展可以收集 Azure 虚拟机的诊断数据。 下**已安装的扩展**，在**选择可用扩展**下拉列表框中，选择**Microsoft 监视代理诊断**。
   
    ![安装 Azure 虚拟机扩展](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC766024.png)
   
    > [!NOTE]
   > 为虚拟机提供了其他诊断扩展。 有关详细信息，请参阅[于 Windows 虚拟机扩展和功能](https://docs.microsoft.com/azure/virtual-machines/windows/extensions-features)。
   > 
   > 
5. 若要添加扩展，并查看其**诊断配置**对话框中，选择**添加**。
6. 若要指定存储帐户，请选择**配置**，然后选择**确定**。
   
    每个选项卡 (除**常规**并**日志目录**) 表示可以收集的诊断数据源。
   
    ![启用 Azure 诊断和配置](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC758144.png)
   
    默认选项卡**常规**，为您提供以下诊断数据收集选项：**仅限错误**，**的所有信息**，和**自定义计划**. 默认选项**仅限错误**，占用最少量的存储空间，因为它不传输警告或跟踪消息。 **的所有信息**选项传输的信息，因此，在存储方面最高的选项。
7. 对于此示例中，选择**自定义计划**选项，以便你可以自定义的数据收集。
8. **以 mb 为单位的磁盘配额**框指定想要分配存储帐户中为诊断数据的空间量。 如果你想，您可以更改默认值。
9. 在你想要收集的诊断数据的每个选项卡上，选择其**启用的传输\<日志类型\>** 复选框。
   
    例如，如果你想要收集应用程序日志，请选择**启用应用程序日志的传输**上的复选框**应用程序日志**选项卡。此外，指定对每个诊断数据类型所需的任何其他信息。 每个选项卡的配置信息，请参阅的部分**设置诊断数据源**这篇文章中更高版本。
10. 启用了所需的所有诊断数据收集后，选择**确定**。
11. 保存已更新的项目。
    
    中的消息**Microsoft Azure 活动日志**窗口指示已更新虚拟机。

## <a name="set-up-diagnostics-data-sources"></a>设置诊断数据源
启用诊断数据收集后，可以选择想要收集，完全哪些数据源和所收集的信息。 后续部分将介绍中的选项卡**诊断配置**对话框中，以及每个配置选项的含义。

### <a name="application-logs"></a>应用程序日志
应用程序日志包含由 web 应用程序生成的诊断信息。 如果你想要捕获应用程序日志，请选择**启用应用程序日志的传输**复选框。 若要增加或减少应用程序日志传输到你的存储帐户之间的间隔，更改**传输周期 （分钟）** 值。 此外可以更改通过设置日志中捕获的信息量**日志级别**值。 例如，选择**Verbose**以获取详细信息，或选择**严重**以仅捕获关键错误。 如果您有特定诊断提供程序来传输应用程序日志，可以通过添加提供程序的 GUID 中捕获的日志**提供程序 GUID**框。

  ![应用程序日志](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC758145.png)

有关应用程序日志的详细信息，请参阅[启用 Azure 应用服务中的 Web 应用的诊断日志记录](/azure/app-service/web-sites-enable-diagnostic-log)。

### <a name="windows-event-logs"></a>Windows 事件日志
若要捕获 Windows 事件日志，请选择**启用 Windows 事件日志的传输**复选框。 若要增加或减少事件日志传输到你的存储帐户之间的间隔，更改**传输周期 （分钟）** 值。 选择你想要跟踪的事件的类型对应的复选框。

![事件日志](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796664.png)

如果使用的 Azure SDK 2.6 或更高版本并想要指定自定义数据源，请输入中**\<数据源名称\>** 文本框中，并选择**添加**。 数据源添加到 diagnostics.cfcfg 文件中。

如果您使用的 Azure SDK 2.5 并想要指定自定义数据源，您可以将其添加到`WindowsEventLog`部分 diagnostics.wadcfgx 文件中，如在下面的示例：

```
<WindowsEventLog scheduledTransferPeriod="PT1M">
   <DataSource name="Application!*" />
   <DataSource name="CustomDataSource!*" />
</WindowsEventLog>
```
### <a name="performance-counters"></a>性能计数器
性能计数器信息可以帮助你找到系统瓶颈以及微调系统和应用程序的性能。 有关详细信息，请参阅[Azure 应用程序中的创建和使用性能计数器](https://msdn.microsoft.com/library/azure/hh411542.aspx)。 若要捕获性能计数器，请选择**启用性能计数器的传输**复选框。 若要增加或减少事件日志传输到你的存储帐户之间的间隔，更改**传输周期 （分钟）** 值。 选择你想要跟踪的性能计数器对应的复选框。

![性能计数器](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC758147.png)

若要跟踪未列出的性能计数器，请使用建议的语法输入性能计数器。 然后选择**添加**。 在虚拟机上的操作系统决定可以跟踪哪些性能计数器。有关语法的详细信息，请参阅[指定计数器路径](https://msdn.microsoft.com/library/windows/desktop/aa373193.aspx)。

### <a name="infrastructure-logs"></a>基础结构日志
基础结构日志包含有关 Azure 诊断基础结构、 RemoteAccess 模块和 RemoteForwarder 模块的信息。 若要收集有关基础结构日志的信息，请选择**启用基础结构日志的传输**复选框。 若要增加或减少基础结构日志传输到你的存储帐户之间的间隔，更改**传输周期 （分钟）** 值。

![诊断基础结构日志](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC758148.png)

有关详细信息，请参阅[使用 Azure 诊断收集日志记录数据](https://msdn.microsoft.com/library/azure/gg433048.aspx)。

### <a name="log-directories"></a>日志目录
日志目录有从 Internet 信息服务 (IIS) 请求、 失败的请求或所选文件夹的日志目录收集的数据。 若要捕获日志目录，选择**启用日志目录的传输**复选框。 若要增加或减少日志传输到你的存储帐户之间的间隔，更改**传输周期 （分钟）** 值。

选中你想要收集，如日志的复选框**IIS 日志**并**失败的请求**日志。 系统提供默认存储容器名称，但可以更改这些名称。

您可以捕获任意文件夹中的日志。 中指定路径**从绝对目录记录**部分中，，然后选择**目录添加**。 日志将在指定的容器。

![日志目录](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796665.png)

### <a name="etw-logs"></a>ETW 日志
如果您使用[Windows 的事件跟踪](https://msdn.microsoft.com/library/windows/desktop/bb968803\(v=vs.85\).aspx)(ETW)，并且想要捕获 ETW 日志，请选中**启用 ETW 日志的传输**复选框。 若要增加或减少日志传输到你的存储帐户之间的间隔，更改**传输周期 （分钟）** 值。

从事件源和您指定的事件清单捕获事件。 若要在指定事件源，**事件源**部分中，输入一个名称，然后选择**添加事件源**。 同样，可以指定事件清单中的**事件清单**部分中，，然后选择**添加事件清单**。

![ETW 日志](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC766025.png)

在 ASP.NET 中通过中的类支持 ETW 框架[并对其进行](https://msdn.microsoft.com/library/system.diagnostics(v=vs.110))命名空间。 Microsoft.WindowsAzure.Diagnostics 命名空间，它继承并扩展了标准[System.Diagnostics.aspx](https://msdn.microsoft.com/library/system.diagnostics(v=vs.110))类，可以使用[并对其进行](https://msdn.microsoft.com/library/system.diagnostics(v=vs.110))作为日志记录在 Azure 环境中的框架。 有关详细信息，请参阅[掌控 Microsoft Azure 中的日志记录和跟踪](https://msdn.microsoft.com/magazine/ff714589.aspx)并[在 Azure 云服务和虚拟机中启用诊断](/azure/cloud-services/cloud-services-dotnet-diagnostics)。

### <a name="crash-dumps"></a>故障转储
若要捕获有关角色实例何时发生故障的信息，请选择**启用故障转储的传输**复选框。 （因为 ASP.NET 处理大多数异常，这是仅对辅助角色通常很有用。）若要增加或减少专用于故障转储的存储空间的百分比，更改**目录配额 （%）** 值。 您可以更改其中故障转储存储，并选择是否想要捕获的存储容器**完整**或**微型**转储。

下面的屏幕截图列出了当前跟踪的进程。 选择你想要捕获的进程对应的复选框。 若要将另一个进程添加到列表中，输入进程名称，然后选择**添加进程**。

![故障转储](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC766026.png)

有关详细信息，请参阅[掌控 Microsoft Azure 中的日志记录和跟踪](https://msdn.microsoft.com/magazine/ff714589.aspx)并[Microsoft Azure 诊断第 4 部分： 自定义日志记录组件和 Azure 诊断 1.3 更改](http://justazure.com/microsoft-azure-diagnostics-part-4-custom-logging-components-azure-diagnostics-1-3-changes/)。

## <a name="view-the-diagnostics-data"></a>查看诊断数据
已收集的云服务或虚拟机的诊断数据后，您可以查看它。

### <a name="to-view-cloud-service-diagnostics-data"></a>若要查看云服务的诊断数据
1. 将照常，云服务部署，然后运行它。
2. 您可以查看诊断中的数据的报表中的 Visual Studio 生成，或在表中您的存储帐户。 到视图的数据在报表中，打开云资源管理器或服务器资源管理器，打开角色，然后选择节点的快捷菜单**查看诊断数据**。
   
    ![查看诊断数据](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC748912.png)
   
    将显示一个报表来显示可用的数据。
   
    ![Visual Studio 中的 Microsoft Azure 诊断报告](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796666.png)
   
    如果未显示的最新数据，您可能需要等待传输周期结束。
   
    若要立即更新数据，请选择**刷新**链接。 若要让数据自动更新，选择在时间间隔**自动刷新**下拉列表框。 若要导出错误数据，请选择**导出到 CSV**按钮以创建可以打开 Excel 工作表中的逗号分隔值文件。
   
    在云资源管理器或服务器资源管理器中，打开与部署相关联的存储帐户。
3. 在表查看器中，打开诊断表，然后查看你收集的数据。 有关 IIS 日志和自定义日志，可以打开 blob 容器。 下表列出了表或 blob 容器包含不同的日志文件的数据。 除了该日志文件的数据，表条目还包含**EventTickCount**， **DeploymentId**，**角色**，以及**RoleInstance**以帮助您识别哪些虚拟机和角色生成数据和时间。 
   
   | 诊断数据 | 描述 | 位置 |
   | --- | --- | --- |
   | 应用程序日志 |你的代码通过调用的方法生成的日志**System.Diagnostics.Trace**类。 |WADLogsTable |
   | 事件日志 |Windows 事件日志中的虚拟机上的数据。 Windows 将信息存储在这些日志，但应用程序和服务还使用日志来报告错误或记录信息。 |WADWindowsEventLogsTable |
   | 性能计数器 |可以是虚拟机上可用的任何性能计数器收集数据。 操作系统提供性能计数器，其中包含许多统计数据，例如内存使用率和处理器时间。 |WADPerformanceCountersTable |
   | 基础结构日志 |从诊断基础结构自身生成的日志。 |WADDiagnosticInfrastructureLogsTable |
   | IIS 日志 |记录 web 请求的日志。 如果你的云服务获取大量的流量，这些日志可能很长。 它是收集和存储此数据，仅在需要时一个好办法。 |您可以找到失败请求日志下 wad-iis-failedreqlogs，有关该部署、 角色和实例路径下的 blob 容器中。 您可以找到 wad iis logfiles 下的完整日志。 为每个文件的条目都在 WADDirectories 表中。 |
   | 故障转储 |提供云服务的进程 （通常为辅助角色） 的二进制映像。 |wad 遇到了转储 blob 容器 |
   | 自定义日志文件 |预定义的数据的日志。 |您可以指定在代码中的自定义日志文件的位置存储帐户中。 例如，可以指定自定义 blob 容器。 |
4. 如果任何类型的数据被截断，可以尝试增大该数据的缓冲区类型或缩短传输的数据从虚拟机到存储帐户之间的间隔。
5. （可选）从存储帐户，降低整体存储开销中清除数据。
6. 执行完整部署时，diagnostics.cscfg 文件 (.wadcfgx Azure SDK 2.5) 会在 Azure 中，并且你的云服务拾取对诊断配置的所有更改。 如果改为更新现有部署，不会在 Azure 中更新.cscfg 文件。 不过，仍可在下一节中的步骤来更改诊断设置。 有关执行完整部署和更新现有部署的详细信息，请参阅[发布 Azure 应用程序向导](vs-azure-tools-publish-azure-application-wizard.md)。

### <a name="to-view-virtual-machine-diagnostics-data"></a>若要查看虚拟机的诊断数据
1. 在虚拟机的快捷菜单，选择**查看诊断数据**。
   
    ![在 Azure 虚拟机中查看诊断数据](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC766027.png)
   
    **诊断摘要**对话框随即出现。
   
    ![Azure 虚拟机诊断摘要](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC796667.png)  
   
    如果未显示的最新数据，您可能需要等待传输周期结束。
   
    若要立即更新数据，请选择**刷新**链接。 若要让数据自动更新，选择在时间间隔**自动刷新**下拉列表框。 若要导出错误数据，请选择**导出到 CSV**按钮以创建可以打开 Excel 工作表中的逗号分隔值文件。

## <a name="set-up-cloud-service-diagnostics-after-deployment"></a>在部署后设置云服务诊断
如果要研究与已在运行的云服务的问题，您可能想要收集数据未指定的最初部署此角色之前。 在这种情况下，可以开始通过更改服务器资源管理器中的设置该数据的收集。 可以设置的单个实例或在角色中，具体取决于是否打开的所有实例的诊断**诊断配置**实例或角色的快捷菜单中的对话框。 如果配置角色节点，所做的任何更改将应用于所有实例。 如果配置实例节点，所做的任何更改仅适用于该实例。

### <a name="to-set-up-diagnostics-for-a-running-cloud-service"></a>若要为正在运行的云服务设置诊断
1. 在服务器资源管理器中，展开**云服务**节点，然后展开节点找到角色或实例 （或两者） 的列表，你想要调查。
   
    ![配置诊断](./media/vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines/IC748913.png)
2. 在实例节点或角色节点的快捷菜单，选择**更新诊断设置**，然后选择你想要收集的诊断设置。
   
    有关配置设置的信息，请参阅明**设置诊断数据源**这篇文章中。 有关如何查看诊断数据的信息，请参阅明**查看诊断数据**这篇文章中。
   
    如果更改服务器资源管理器中的数据收集，所做的更改之前保持有效完全重新部署你的云服务。 如果使用默认发布设置，不会覆盖所做的更改。 默认的发布设置是要更新现有部署，而不执行完全重新部署。 若要确保设置在部署时清除，请转到**高级设置**发布向导中选项卡，然后清除**部署更新**复选框。 当您重新部署并清除该复选框时，请设置将还原为.wadcfgx （或.wadcfg） 文件中是通过**属性**编辑器的角色。 如果更新部署，Azure 会保留早期设置。

## <a name="troubleshoot-azure-cloud-service-issues"></a>对 Azure 云服务问题进行故障排除
如果遇到问题的云服务项目，例如陷入"繁忙"状态的角色反复回收或引发内部服务器错误，一些工具和技术，可用于诊断和修复此问题。 有关的常见问题和解决方案，具体示例和概念和工具，可用于诊断和修复这些错误的概述，请参阅[Azure PaaS 计算诊断数据](http://blogs.msdn.com/b/kwill/archive/2013/08/09/windows-azure-paas-compute-diagnostics-data.aspx)。

## <a name="q--a"></a>问题解答
**什么是缓冲区大小，以及如何大型应设置为？**

每个虚拟机实例，在配额限制多少诊断数据可以存储在本地文件系统上。 此外，您可以指定每种类型的可用诊断数据的缓冲区大小。 此缓冲区大小的作用类似的该类型的数据配额。 若要确定整体配额和剩余内存量，请参阅的诊断数据类型对话框的底部。 如果指定更大的缓冲区或更多类型的数据，便越接近整体配额。 可以通过修改 diagnostics.wadcfg 或.wadcfgx 配置文件更改整体配额。 诊断数据存储在与应用程序的数据相同的文件系统上。 如果应用程序使用大量的磁盘空间，不应增加整体诊断配额。

**什么是传输周期，以及应为多长？**

传输周期为数据捕获之间经过的时间量。 每个传输周期，数据移动后从本地文件系统上虚拟机到存储帐户中的表。 如果在传输周期结束之前，收集的数据量超过配额，则丢弃较旧的数据。 如果由于超出缓冲区大小或整体配额而丢失数据，你可能想要缩短传输周期。

**中的时间戳哪个时区？**

时间戳是以托管你的云服务的数据中心的本地时区。 使用下面的三个时间戳列中的日志表：

* **PreciseTimeStamp**： 该事件的 ETW 时间戳。 也就是说，从客户端记录的事件的时间。
* **时间戳**： 为值**PreciseTimeStamp**上传频率边界向下舍入。 例如，如果上传频率为 5 分钟，事件时间为 00:17:12，时间戳是 00:15:00。
* **时间戳**： 在 Azure 表中创建实体时的时间戳。

**收集诊断信息时，如何管理开销？**

默认设置 (**日志级别**设置为**错误**，并**传输周期**设置为**1 分钟**) 旨在最小化成本。 计算成本增加时收集诊断数据越多，或缩短传输周期。 不收集更多的数据不是所需，并且不要忘记在不再需要时禁用数据收集。 你可以始终再次启用它，即使在运行时，如本文前面部分中所述。

**如何从 IIS 收集失败请求日志？**

默认情况下，IIS 不会收集失败请求日志。 可以设置 IIS 收集失败请求日志通过编辑你的 web 角色的 web.config 文件。

**我不从 OnStart 等 RoleEntryPoint 方法获得跟踪信息。怎么了？**

方法**RoleEntryPoint** WAIISHost.exe，不在 IIS 中的上下文中调用。 通常情况下启用跟踪不会应用的 web.config 中的配置信息。 若要解决此问题，将.config 文件添加到 web 角色项目，并将文件以匹配输出程序集包含命名**RoleEntryPoint**代码。 在默认 web 角色项目中，.config 文件的名称应该是 WAIISHost.exe.config。将以下行添加到此文件：

```
<system.diagnostics>
  <trace>
      <listeners>
          <add name “AzureDiagnostics” type=”Microsoft.WindowsAzure.Diagnostics.DiagnosticMonitorTraceListener”>
              <filter type=”” />
          </add>
      </listeners>
  </trace>
</system.diagnostics>
```

在中**属性**窗口中，将**复制到输出目录**属性设置为**始终复制**。

## <a name="next-steps"></a>后续步骤
若要了解有关 Azure 中诊断日志记录的详细信息，请参阅[在 Azure 云服务和虚拟机中启用诊断](/azure/cloud-services/cloud-services-dotnet-diagnostics.md)并[启用 Azure 应用服务中的 Web 应用的诊断日志记录](/azure/app-service/web-sites-enable-diagnostic-log)。

