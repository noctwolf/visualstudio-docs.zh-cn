---
title: 测试云服务的性能 |Microsoft Docs
description: 测试使用 Visual Studio 探查器的云服务的性能
author: mikejo5000
manager: douge
ms.assetid: 7a5501aa-f92c-457c-af9b-92ea50914e24
ms.topic: conceptual
ms.tgt_pltfrm: multiple
ms.workload: na
ms.date: 11/11/2016
ms.author: mikejo
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.openlocfilehash: 25b60e5e4072a0523d17082a5c5646e5bb1ade6a
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001418"
---
# <a name="testing-the-performance-of-a-cloud-service"></a>测试云服务的性能
## <a name="overview"></a>概述
你可以按以下方式测试云服务的性能：

* 使用 Azure 诊断以收集有关请求和连接信息并查看显示的服务执行从客户角度来看的站点统计信息。 若要开始使用，请参阅[为 Azure 云服务和虚拟机配置诊断](http://go.microsoft.com/fwlink/p/?LinkId=623009)。
* 使用 Visual Studio 探查器来获取该服务的运行方式在计算方面的深入分析。 如本主题中所述，可以使用探查器来测量性能服务在 Azure 中运行。 有关如何使用探查器来测量性能，因为在计算模拟器中本地运行服务的信息，请参阅[测试的 Azure 云服务本地性能，在计算仿真程序使用 Visual Studio Profiler](http://go.microsoft.com/fwlink/p/?LinkId=262845).

## <a name="choosing-a-performance-testing-method"></a>选择性能测试方法
### <a name="use-azure-diagnostics-to-collect"></a>使用 Azure 诊断收集：
* 对网页或服务，如请求和连接统计信息。
* 角色，例如角色重启何种频率对统计信息。
* 总体内存使用情况，例如垃圾回收器所花费的时间或内存的百分比信息设置的正在运行的角色。

### <a name="use-the-visual-studio-profiler-to"></a>使用 Visual Studio 探查器附加到：
* 确定哪些函数需要最多时间。
* 度量值计算密集型程序的每个部分需要花费多少时间。
* 比较两个版本的服务的详细的性能报告。
* 分析内存分配比单个内存分配级别的更多详细信息。
* 分析多线程代码中的并发问题。

当使用探查器时，可以收集数据，当云服务在本地或 Azure 中运行时。

### <a name="collect-profiling-data-locally-to"></a>收集分析数据保存在本地到：
* 测试云服务，如特定辅助角色，但不需要实际模拟的负载的执行的一部分的性能。
* 在隔离中，在受控的情况下测试云服务的性能。
* 部署到 Azure 之前，请测试云服务的性能。
* 私下，测试云服务的性能，而不影响现有的部署。
* 无需支付费用在 Azure 中运行测试服务的性能。

### <a name="collect-profiling-data-in-azure-to"></a>收集在 Azure 中的分析数据：
* 测试云服务在模拟或真实负载下的性能。
* 使用检测方法收集的分析数据，如本主题介绍了更高版本。
* 在与该服务在生产环境中的运行时相同的环境中测试服务的性能。

通常会通过模拟一个负载，测试云服务下正常或压力状况。

## <a name="profiling-a-cloud-service-in-azure"></a>分析在 Azure 中的云服务
当你从 Visual Studio 的云服务发布时，可以配置文件服务，并指定为你提供所需的信息的分析设置。 为每个角色实例启动分析会话。 有关如何从 Visual Studio 中发布服务的详细信息，请参阅[从 Visual Studio 发布到 Azure 云服务](https://msdn.microsoft.com/library/azure/ee460772.aspx)。

若要了解有关 Visual Studio 中的性能分析的详细信息，请参阅[性能分析初学者指南](https://msdn.microsoft.com/library/azure/ms182372.aspx)并[使用分析工具分析应用程序性能](https://msdn.microsoft.com/library/azure/z9z62c29.aspx)。

> [!NOTE]
> 可以启用 IntelliTrace 或分析时发布云服务。 不能同时启用。
> 
> 

### <a name="profiler-collection-methods"></a>Profiler 收集方法
您可以使用不同的集合方法进行分析，基于性能问题：

* **CPU 采样**-此方法收集用于 CPU 利用率问题的初始分析的应用程序统计信息。 CPU 采样是用于启动大多数性能调查的建议的方法。 收集 CPU 采样数据时要分析的应用程序中没有较大影响。
* **检测**-此方法收集用于重点分析和分析输入/输出性能问题有用的详细的计时数据。 检测方法记录每个条目、 退出和函数调用的函数的模块中分析期间运行。 此方法适用于收集有关代码中某个部分的详细计时信息，以及了解输入和输出操作对应用程序性能的影响。 对于运行 32 位操作系统的计算机禁用此方法。 仅当你的云服务在 Azure 中运行，不是本地计算仿真程序中时，此选项才可用。
* **.NET 内存分配**-此方法通过使用采样分析方法收集.NET Framework 内存分配数据。 收集的数据包括数量和大小分配的对象。
* **并发**-此方法收集资源争用数据和用于分析多线程和多进程应用程序的进程和线程执行数据。 并发方法收集阻止代码执行（如线程等待释放对应用程序资源的锁定访问时）的每个事件的数据。 此方法对分析多线程应用程序很有用。
* 您还可以启用**层交互分析**，其中提供了其他信息的执行时间的同步 ADO.NET 调用在函数中的多层应用程序与一个或多个数据库进行通信。 可以使用任意分析方法收集层交互数据。 有关层交互分析的详细信息，请参阅[层交互视图](https://msdn.microsoft.com/library/azure/dd557764.aspx)。

## <a name="configuring-profiling-settings"></a>配置分析设置
下图显示如何配置分析设置发布 Azure 应用程序对话框中。

![配置分析设置](./media/vs-azure-tools-performance-profiling-cloud-services/IC526984.png)

> [!NOTE]
> 若要启用**启用分析**复选框，您必须具有用来发布云服务在本地计算机上安装了探查器。 默认情况下，安装 Visual Studio 时会安装探查器。
> 
> 

### <a name="to-configure-profiling-settings"></a>若要配置分析设置
1. 在解决方案资源管理器，打开 Azure 项目的快捷菜单，然后选择**发布**。 有关如何发布云服务的详细步骤，请参阅[发布云服务使用的 Azure 工具](http://go.microsoft.com/fwlink/p?LinkId=623012)。
2. 在中**发布 Azure 应用程序**对话框中，选择**高级设置**选项卡。
3. 若要启用分析，请选择**启用分析**复选框。
4. 若要配置分析设置，请选择**设置**超链接。 将显示分析设置对话框。
5. 从**要使用什么分析方法**选项按钮中，选择所需的分析类型。
6. 若要收集层交互分析数据，请选择**启用层交互分析**复选框。
7. 若要保存设置，请选择**确定**按钮。
   
    当发布此应用程序时，这些设置用于创建分析会话的每个角色。

## <a name="viewing-profiling-reports"></a>查看分析报告
为你的云服务中的角色的每个实例创建分析会话。 若要查看的每个会话中从 Visual Studio 的分析报告，您可以查看服务器资源管理器窗口，然后选择要选择的角色实例的 Azure 计算节点。 下图中所示，然后可以查看分析报告。

![从 Azure 查看分析报告](./media/vs-azure-tools-performance-profiling-cloud-services/IC748914.png)

### <a name="to-view-profiling-reports"></a>若要查看分析报告
1. 若要在 Visual Studio 中查看服务器资源管理器窗口，请在菜单栏上选择视图中，服务器资源管理器。
2. 选择 Azure 计算节点，然后选择您选择配置文件从 Visual Studio 发布云服务的 Azure 部署节点。
3. 若要查看实例分析报告，请选择角色服务中，打开特定实例的快捷菜单，然后选择**查看分析报告**。
   
    从 Azure 中，现在下载报表，一个.vsp 文件，并下载状态显示在 Azure 活动日志。 下载完成后，分析报告将显示的选项卡中的名为的 Visual Studio 编辑器<Role name> *<Instance Number>* <identifier>.vsp。 将显示报表的摘要数据。
4. 若要在当前视图列表中显示报表的不同视图，请选择所需视图类型。 有关详细信息，请参阅[分析工具报告视图](https://msdn.microsoft.com/library/azure/bb385755.aspx)。

## <a name="next-steps"></a>后续步骤
[调试云服务](https://msdn.microsoft.com/library/azure/ee405479.aspx)

[从 Visual Studio 发布到 Azure 云服务](https://msdn.microsoft.com/library/azure/ee460772.aspx)

