---
title: 浏览和使用服务器资源管理器管理存储资源 |Microsoft Docs
description: 浏览和使用服务器资源管理器管理存储资源
author: ghogen
manager: douge
assetId: 658dc064-4a4e-414b-ae5a-a977a34c930d
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 8/24/2017
ms.author: ghogen
ms.openlocfilehash: 00229cd88ddcab4d2d59ae40202620c374415e4b
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001590"
---
# <a name="browse-and-manage-storage-resources-by-using-server-explorer"></a>使用服务器资源管理器浏览和管理存储资源

[!INCLUDE [storage-try-azure-tools](./includes/storage-try-azure-tools.md)]

## <a name="overview"></a>概述

如果你已安装 Azure Tools for Microsoft Visual Studio，您可以查看 blob、 队列和表数据从你的存储帐户用于 Azure。 Azure**存储**在服务器资源管理器中的节点显示了在本地存储模拟器帐户和其他 Azure 存储帐户中的数据。

若要查看服务器资源管理器在 Visual Studio 中，在菜单栏上，选择**视图** > **服务器资源管理器**。 **存储**节点显示的所有存储帐户下的每个 Azure 订阅或已连接到的证书。 如果未显示你的存储帐户，可以将其添加的说明[这篇文章中更高版本](#add-storage-accounts-by-using-server-explorer)。

从 Azure SDK 2.7 开始，你还可用于云资源管理器查看和管理 Azure 资源。 有关详细信息，请参阅[使用云资源管理器管理 Azure 资源](vs-azure-tools-resources-managing-with-cloud-explorer.md)。

## <a name="view-and-manage-storage-resources-in-visual-studio"></a>查看和管理 Visual Studio 中的存储资源

服务器资源管理器会自动显示存储模拟器帐户中的 blob、 队列和表的列表。 存储模拟器帐户在服务器资源管理器中列出**存储**节点作为**开发**节点。

若要查看存储模拟器帐户的资源，请展开**开发**节点。 当您展开时，如果尚未启动存储模拟器**开发**节点，它会自动启动。 此过程可能需要数秒钟的时间。 您可以继续在 Visual Studio 的其他区域中工作，存储模拟器启动时。

若要查看存储帐户中的资源，请展开存储帐户的节点在服务器资源管理器将出现**Blob**，**队列**，并**表**节点。

## <a name="work-with-blob-resources"></a>处理 blob 资源

**Blob**节点显示所选的存储帐户的容器列表。 Blob 容器包含 blob 文件，并可以将这些 blob 组织成文件夹和子文件夹。 有关详细信息，请参阅[如何通过.NET 使用 Blob 存储](/azure/storage/blobs/storage-dotnet-how-to-use-blobs)。

### <a name="to-create-a-blob-container"></a>若要创建 blob 容器

1. 打开快捷菜单**Blob**节点，并选择**创建 Blob 容器**。
1. 在中**创建 Blob 容器**对话框框中，输入新容器的名称。  
1. 单击或点击名称字段即可保存 blob 容器以外的键盘，或您选择 Enter。

   > [!NOTE]
   > Blob 容器名称必须以数字 (0-9) 或小写字母 (a 到 z) 开头。

### <a name="to-delete-a-blob-container"></a>若要删除 blob 容器

打开你想要删除，然后选择 blob 容器的快捷菜单**删除**。

### <a name="to-display-a-list-of-the-items-in-a-blob-container"></a>若要在 blob 容器中显示的项的列表

在列表中，打开 blob 容器名称的快捷菜单，然后选择**打开**。

当您查看 blob 容器的内容时，它称为 blob 容器视图选项卡上显示。

![Blob 容器视图](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC749016.png)

可以通过使用中的 blob 容器视图右上角的按钮执行对 blob 执行以下操作：

* 输入筛选器值并将其应用。
* 刷新容器中的 blob 列表。
* 上传文件。
* 删除 blob。 （从 blob 容器中删除文件不会删除基础文件。 它只会删除它从 blob 容器。）
* 打开 blob。
* 将 blob 保存到本地计算机。

### <a name="to-create-a-folder-or-subfolder-in-a-blob-container"></a>若要在 blob 容器中创建文件夹或子文件夹

1. 在云资源管理器中选择 blob 容器。 在容器窗口中，选择**上传 Blob**按钮。

1. 在中**上传新文件**对话框中，选择**浏览**按钮并指定你想要上传，该文件，然后输入中的文件夹名**文件夹 （可选）** 框。

   ![将文件上传到 blob 文件夹](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC766037.png)

   按照相同步骤，可以在容器文件夹中添加子文件夹。 如果未指定文件夹名称，将文件上载到 blob 容器的顶层。 该文件将显示在容器中指定的文件夹中。

   ![文件夹添加到 blob 容器](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC766038.png)

1. 双击文件夹或按 Enter 查看文件夹的内容。 容器的文件夹中时，你可以返回到容器的根目录通过选择**打开父目录**（箭头） 按钮。

### <a name="to-delete-a-container-folder"></a>若要删除容器文件夹

删除文件夹中的所有文件。

由于 blob 容器中的文件夹是虚拟文件夹，不能创建一个空文件夹。 您还不能删除文件夹并删除其文件内容，而是必须删除文件夹并删除文件夹本身的全部内容。

### <a name="to-filter-blobs-in-a-container"></a>若要筛选容器中的 blob

您可以筛选所显示的指定公共前缀的 blob。

例如，如果输入前缀**你好**在筛选器文本框中，然后选择**Execute** (**！**) 按钮，会显示"你好"开头的 blob。

![筛选器文本框中](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC519076.png)

筛选器文本框中区分大小写，不支持使用通配符筛选。 只能按前缀筛选 blob。 如果使用分隔符来组织虚拟层次结构中的 blob，则前缀可以包含分隔符。 例如，筛选针对前缀"HelloFabric /"返回该字符串开头的所有 blob。

### <a name="to-download-blob-data"></a>若要下载 blob 数据

在云资源管理器，使用以下方法之一：

* 打开一个或多个 blob 的快捷菜单，然后选择**打开**。
* 选择 blob 名称，然后选择**打开**按钮。
* 双击 blob 名称。

Blob 下载的进度会显示在**Azure 活动日志**窗口。

此文件类型的默认编辑器中打开该 blob。 如果操作系统识别出的文件类型，在本地安装的应用程序中打开该文件。 否则，系统会提示选择适合该 blob 的文件类型的应用程序。 下载 blob 时创建的本地文件标记为只读的。

Blob 数据在本地缓存，并根据 Azure Blob 存储中 blob 的上次修改时间检查。 如果自上次下载以来已更新 blob，则将再次下载。 否则，从本地磁盘加载 blob。

默认情况下，blob 下载到临时目录中。 若要将 blob 下载到特定目录中，打开所选的 blob 名称的快捷菜单，然后选择**另存为**。 以这种方式保存 blob 时，无法打开 blob 文件，并具有读/写属性创建的本地文件。

### <a name="to-upload-blobs"></a>若要将 blob 上传

若要上传 blob，请选择**上传 Blob**按钮时在容器处于打开状态，在 blob 容器视图中查看。

您可以选择一个或多个文件进行上传，并可以上传任何类型的文件。 **Azure 活动日志**窗口显示上传进度。 有关如何处理 blob 数据的详细信息，请参阅[如何在.NET 中使用 Azure Blob 存储](http://go.microsoft.com/fwlink/p/?LinkId=267911)。

### <a name="to-view-logs-transferred-to-blobs"></a>若要查看日志传输到 blob

如果正在使用 Azure 诊断来记录 Azure 应用程序中的数据，并且已将日志传输到存储帐户，则会看到 Azure 为这些日志创建的容器。 在服务器资源管理器中查看这些日志是轻松地确定应用程序的问题，尤其已部署到 Azure。

有关 Azure 诊断的详细信息，请参阅[使用 Azure 诊断收集日志记录数据](https://msdn.microsoft.com/library/azure/gg433048.aspx)。

### <a name="to-get-the-url-for-a-blob"></a>若要获取 blob 的 URL

打开 blob 的快捷菜单，然后选择**复制 URL**。

### <a name="to-edit-a-blob"></a>若要编辑 blob

选择 blob，然后选择**打开 Blob**按钮。

该文件已下载到临时位置，在本地计算机上打开。 再次上传 blob 后进行更改。

## <a name="work-with-queue-resources"></a>处理队列资源

存储服务队列托管在 Azure 存储帐户中。 可以使用它们，允许你的云服务角色进行通信以及与其他服务的消息传递机制。 通过云服务和外部客户端的 web 服务，可以以编程方式访问队列。 此外可以直接通过 Visual Studio 中使用服务器资源管理器来访问队列。

当开发使用队列的云服务时，你可能想要使用 Visual Studio 来创建队列，并使用它们以交互方式开发和测试你的代码时。

在服务器资源管理器，可以查看存储帐户中的队列、 创建和删除队列、 打开队列以查看其消息和向队列添加消息。 当您打开队列进行查看时，可以查看各条消息，并可以通过在左上角中使用的按钮在队列中执行以下操作：

* 刷新队列的视图。
* 向队列添加消息。
* 取消顶部消息的排队。
* 清除整个队列。

下图显示了包含两条消息的队列：

![查看队列](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC651470.png)

详细了解存储服务队列，请参阅[开始使用 Azure 队列存储通过.NET](http://go.microsoft.com/fwlink/?LinkID=264702)。 有关 web 服务信息存储服务队列，请参阅[队列服务概念](http://go.microsoft.com/fwlink/?LinkId=264788)。 有关如何使用 Visual Studio 将消息发送到存储服务队列的信息，请参阅[将消息发送到存储服务队列](https://docs.microsoft.com/azure/visual-studio/vs-storage-cloud-services-getting-started-queues)。

> [!NOTE]
> 存储服务队列是不同于 Azure 服务总线队列。 有关服务总线队列的详细信息，请参阅[服务总线队列、 主题和订阅](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-queues-topics-subscriptions)。

## <a name="work-with-table-resources"></a>处理表资源

Azure 表存储可存储大量结构化数据。 该服务是一种 NoSQL 数据存储，接受来自经过身份验证的呼叫 Azure 云内部和外部。 Azure 表非常适合存储结构化非关系型数据。

### <a name="to-create-a-table"></a>要创建表

1. 在云资源管理器中，选择**表**节点的存储帐户，然后选择**Create Table**。
1. 在中**Create Table**对话框框中，输入表的名称。

### <a name="to-view-table-data"></a>若要查看表数据

1. 在云资源管理器中打开**Azure**节点，然后再打开**存储**节点。
1. 打开你感兴趣，然后打开的存储帐户节点**表**节点以查看存储帐户的表列表。
1. 打开表的快捷菜单，然后选择**视图表**。

    ![解决方案资源管理器中的 Azure 表](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC744165.png)

该表按实体 （行中所示） 和属性 （列中所示）。 例如下, 图显示在表设计器中列出的实体。

### <a name="to-edit-table-data"></a>编辑表数据

在表设计器中打开实体 （单行） 或属性 （单个单元） 的快捷菜单，然后选择**编辑**。

    ![Add or edit a table entity](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC656238.png)

单个表中的实体不需要具有相同的属性 （列） 集。 请记住在查看和编辑表数据的以下限制：

* 不能查看或编辑二进制数据 (`type byte[]`)，但可以将其存储在表中。
* 不能编辑**PartitionKey**或**RowKey**值，因为表存储在 Azure 中的不支持该操作。
* 不能创建一个名为属性**时间戳**。 Azure 存储服务使用具有该名称的属性。
* 如果输入**DateTime**值，则必须按照适合于您的计算机的区域和语言设置的格式 (例如，MM/DD/YYYY hh: mm: [AM |PM] 为美国英语)。

### <a name="to-add-entities"></a>添加实体

1. 在表设计器中，选择**添加实体**按钮。

    ![添加实体按钮](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC655336.png)

1. 在中**添加实体**对话框框中，输入的值**PartitionKey**并**RowKey**属性。

    ![添加实体对话框](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC655335.png)

    输入值时应小心。 除非删除此实体，再次将其添加关闭对话框后，便不能更改它们。

### <a name="to-filter-entities"></a>若要筛选实体

您可以自定义显示在表中，如果使用查询生成器的实体集。

1. 若要打开查询生成器，请打开表进行查看。
1. 选择**查询生成器**表视图工具栏上的按钮。

    **查询生成器**对话框随即出现。 下图显示查询生成器中正在生成的查询。

    ![查询生成器](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC652231.png)
1. 完成后生成查询，关闭对话框。 在文本框中，查询的结果的文本窗体显示为 WCF 数据服务筛选器。
1. 若要运行查询，请选择绿色三角形图标。

此外可以筛选显示在表设计器如果输入 WCF 数据服务筛选器字符串直接在筛选器文本框中的实体数据。 此类字符串类似于 SQL WHERE 子句，但发送到作为 HTTP 请求服务器。 有关如何构建筛选器字符串的信息，请参阅[Constructing 的表设计器的筛选器字符串](https://docs.microsoft.com/azure/vs-azure-tools-table-designer-construct-filter-strings)。

下图显示了有效的筛选器字符串的示例：

![筛选器字符串](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC655337.png)

## <a name="refresh-storage-data"></a>刷新存储数据

当服务器资源管理器连接到或从存储帐户获取数据时，该操作可能需要一分钟的时间才能完成。 如果服务器资源管理器无法连接，则操作可能会超时。在检索数据，您可以继续在 Visual Studio 的其他部分中。 若要取消操作，如果时间太长，请选择**停止刷新**服务器资源管理器工具栏上的按钮。

### <a name="to-refresh-blob-container-data"></a>若要刷新 blob 容器数据

* 选择**Blob**下面的节点**存储**，然后选择**刷新**服务器资源管理器工具栏上的按钮。
* 若要刷新显示的 blob 列表，请选择**Execute**按钮。

### <a name="to-refresh-table-data"></a>若要刷新表数据

* 选择**表**下面的节点**存储**，然后选择**刷新**服务器资源管理器工具栏上的按钮。
* 若要刷新显示在表设计器中的实体列表，请选择**Execute**表设计器中的按钮。

### <a name="to-refresh-queue-data"></a>若要刷新队列数据

选择**队列**下面的节点**存储**，然后选择**刷新**服务器资源管理器工具栏上的按钮。

### <a name="to-refresh-all-items-in-a-storage-account"></a>若要刷新存储帐户中的所有项

选择帐户名称，然后选择**刷新**服务器资源管理器工具栏上的按钮。

## <a name="add-storage-accounts-by-using-server-explorer"></a>使用服务器资源管理器添加存储帐户

有两种方法来使用服务器资源管理器添加存储帐户。 可以在 Azure 订阅中创建存储帐户，也可以附加现有的存储帐户。

### <a name="to-create-a-storage-account-by-using-server-explorer"></a>若要使用服务器资源管理器创建存储帐户

1. 在服务器资源管理器中打开的快捷菜单**存储**节点，并选择**创建存储帐户**。

1. 在中**创建存储帐户**对话框框中，选择或输入以下信息：

   * 你想要添加的存储帐户的 Azure 订阅。
   * 你想要用于新的存储帐户名称。
   * 区域或地缘组 （如美国西部或亚洲东部）。
   * 类型的复制你想要使用的存储帐户，如本地冗余。

   ![创建 Azure 存储帐户](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC744166.png)

1. 选择“创建”。

新的存储帐户将出现**存储**在解决方案资源管理器的列表。

### <a name="to-attach-an-existing-storage-account-by-using-server-explorer"></a>若要使用服务器资源管理器附加现有的存储帐户

1. 在服务器资源管理器中打开快捷菜单，Azure**存储**节点，并选择**附加外部存储**。

    ![添加现有的存储帐户](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC766039.png)
1. 在中**创建存储帐户**对话框框中，选择或输入以下信息：

   * 你想要附加的现有存储帐户的名称。
   * 所选的存储帐户的密钥。 选择存储帐户时，您通常提供此值。 如果您希望 Visual Studio 记住存储帐户密钥，选择**记住帐户密钥**复选框。
   * 要用于连接到存储帐户，如 HTTP、 HTTPS 或自定义终结点的协议。 有关自定义终结点的详细信息，请参阅[如何配置连接字符串](https://msdn.microsoft.com/library/azure/ee758697.aspx)。

### <a name="to-view-the-secondary-endpoints"></a>若要查看辅助终结点

如果使用创建存储帐户**读取访问异地冗余**复制选项，您可以通过打开帐户名称的快捷菜单来查看其辅助终结点，然后选择**属性**.

![存储辅助终结点](./media/vs-azure-tools-storage-resources-server-explorer-browse-manage/IC766040.png)

### <a name="to-remove-a-storage-account-from-server-explorer"></a>若要从服务器资源管理器中删除存储帐户

在服务器资源管理器，打开帐户名称的快捷菜单，然后选择**删除**。 

如果删除存储帐户，还会删除该帐户的任何已保存的密钥信息。

如果从服务器资源管理器删除存储帐户，它不会影响你的存储帐户或它所包含的任何数据。 它只需从服务器资源管理器中删除引用。 若要永久删除存储帐户，请使用[Azure 门户](https://portal.azure.com/)。

## <a name="next-steps"></a>后续步骤

若要了解有关如何使用 Azure 存储服务的详细信息，请参阅[访问 Azure 存储服务](https://msdn.microsoft.com/library/azure/ee405490.aspx)。
