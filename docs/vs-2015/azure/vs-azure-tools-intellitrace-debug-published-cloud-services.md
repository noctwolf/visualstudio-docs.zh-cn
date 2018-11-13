---
title: 调试已发布的 Azure 云服务与 Visual Studio 和 IntelliTrace |Microsoft Docs
description: 了解如何调试云服务与 Visual Studio 和 IntelliTrace
author: mikejo5000
manager: douge
ms.assetid: 5e6662fc-b917-43ea-bf2b-4f2fc3d213dc
ms.topic: conceptual
ms.custom: vs-azure
ms.workload: azure-vs
ms.date: 03/21/2017
ms.author: mikejo
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.openlocfilehash: 865642bb7c8e41f81ff4b44ce628082e19b63a56
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001570"
---
# <a name="debugging-a-published-azure-cloud-service-with-visual-studio-and-intellitrace"></a>使用 Visual Studio 和 IntelliTrace 调试已发布的 Azure 云服务
使用 IntelliTrace，可以在 Azure 中运行时记录的角色实例的大量调试信息。 如果你需要找出问题的原因，可以使用 IntelliTrace 日志来单步执行您的代码从 Visual Studio 好像它在 Azure 中运行。 实际上，IntelliTrace 将记录关键代码执行和环境数据时 Azure 应用程序作为云服务在 Azure 中运行，并可以重播从 Visual Studio 记录的数据。 

可以使用 IntelliTrace，如果已安装的 Visual Studio Enterprise 和 Azure 应用程序所针对.NET Framework 4 或更高版本。 IntelliTrace 将收集有关您的 Azure 角色的信息。 这些角色的虚拟机始终运行 64 位操作系统。

作为替代方法，你可以使用[远程调试](http://go.microsoft.com/fwlink/p/?LinkId=623041)，直接连接到在 Azure 中运行的云服务。

> [!IMPORTANT]
> IntelliTrace 仅适用于调试方案，并不用于生产部署。
> 

## <a name="configure-an-azure-application-for-intellitrace"></a>为 IntelliTrace 配置 Azure 应用程序
若要为 Azure 应用程序启用 IntelliTrace，必须创建并发布应用程序从 Visual Studio Azure 项目。 发布到 Azure 之前，必须为 Azure 应用程序中配置 IntelliTrace。 如果不配置 IntelliTrace 发布应用程序，您需要重新发布项目。 有关详细信息，请参阅[发布 Azure 云服务项目使用 Visual Studio](http://go.microsoft.com/fwlink/p/?LinkId=623012)。

1. 当准备好部署 Azure 应用程序，验证是否将项目生成目标设置为**调试**。

1. 在中**解决方案资源管理器**，右键单击项目，并从上下文菜单中，选择**发布**。
   
1. 在中**发布 Azure 应用程序**对话框中，选择 Azure 订阅，并选择**下一步**。

1. 在中**设置**页上，选择**高级设置**选项卡。

1. 开启**启用 IntelliTrace**选项可在云中发布时收集你的应用程序的 IntelliTrace 日志。
   
1. 若要自定义基本 IntelliTrace 配置，请选择**设置**旁边**启用 IntelliTrace**。

    ![IntelliTrace 设置链接](./media/vs-azure-tools-intellitrace-debug-published-cloud-services/intellitrace-settings-link.png)
   
1. 在中**IntelliTrace 设置**对话框中，可以指定哪些事件、 是否收集调用信息、 模块和过程来收集日志，以及分配给记录的空间大小。 有关 IntelliTrace 的详细信息，请参阅[使用 IntelliTrace 进行调试](http://go.microsoft.com/fwlink/?LinkId=214468)。
   
    ![IntelliTrace 设置](./media/vs-azure-tools-intellitrace-debug-published-cloud-services/IC519063.png)

IntelliTrace 日志是 IntelliTrace 设置 （默认大小为 250 MB） 中指定的最大大小的循环日志文件。 IntelliTrace 日志收集到的虚拟机的文件系统中的文件。 当请求日志时，快照执行点的时间，并下载到本地计算机。

Azure 云服务发布到 Azure 后，可以确定是否中的 Azure 节点从启用了 IntelliTrace**服务器资源管理器**下, 图中所示：

![服务器资源管理器-启用 IntelliTrace](./media/vs-azure-tools-intellitrace-debug-published-cloud-services/IC744134.png)

## <a name="download-intellitrace-logs-for-a-role-instance"></a>下载角色实例的 IntelliTrace 日志
使用 Visual Studio，您可以通过执行以下步骤来下载角色实例的 IntelliTrace 日志：

1. 在中**服务器资源管理器**，展开**云服务**节点，并找到角色实例以下载所需的日志。 

1. 右键单击该角色实例，并从上下文菜单中选择**查看 IntelliTrace 日志**。 

    ![查看 IntelliTrace 日志菜单选项](./media/vs-azure-tools-intellitrace-debug-published-cloud-services/view-intellitrace-logs.png)

1. IntelliTrace 日志下载到本地计算机上的文件的目录中。 每次请求 IntelliTrace 日志，创建新的快照。 正在下载日志，而 Visual Studio 将显示在操作的进度**Azure 活动日志**窗口。 下图中所示，您可以展开操作以查看更多详细信息行项。

![VST_IntelliTraceDownloadProgress](./media/vs-azure-tools-intellitrace-debug-published-cloud-services/IC745551.png)

您可以继续下载 IntelliTrace 日志时，在 Visual Studio 中工作。 日志下载完成后，它将在 Visual Studio 中打开。

> [!NOTE]
> IntelliTrace 日志可能包含由框架生成并进行后续处理的异常。 内部框架代码生成的正常一环的启动角色，因此可以放心地忽略这些异常。
> 
> 

## <a name="next-steps"></a>后续步骤
- [调试 Azure 云服务的选项](vs-azure-tools-debugging-cloud-services-overview.md)
- [发布 Azure 云服务使用 Visual Studio](vs-azure-tools-publishing-a-cloud-service.md)