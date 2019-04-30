---
title: 调试实时 ASP.NET Azure 虚拟机和 Azure 虚拟机规模集
description: 了解如何使用 Snapshot Debugger 设置快照点并查看快照。
ms.custom: ''
ms.date: 02/06/2019
ms.topic: conceptual
helpviewer_keywords:
- debugger
author: poppastring
ms.author: madownie
manager: andster
monikerRange: '>= vs-2019'
ms.workload:
- aspnet
- azure
ms.openlocfilehash: 2880b8bee25a79f5f182043ffed5c50c4512d033
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63399425"
---
# <a name="debug-live-aspnet-apps-on-azure-virtual-machines-and-azure-virtual-machine-scale-sets-using-the-snapshot-debugger"></a>使用 Snapshot Debugger 在 Azure 虚拟机和 Azure 虚拟机规模集上调试实时 ASP.NET 应用

Snapshot Debugger 会在你感兴趣的代码执行时为生产中的应用拍摄快照。 若要指示该调试器拍摄快照，可以在代码中设置快照点和记录点。 通过该调试器，可精确查看出错的内容，而不会影响生产应用程序的流量。 Snapshot Debugger 有助于大幅减少解决生产环境中出现的问题所需的时间。

快照点和记录点类似于断点，但与断点不同的是，快照点不会在命中时停止应用程序。 通常，在快照点捕获快照需要 10-20 毫秒。

在本教程中，你将：

> [!div class="checklist"]
> * 启动 Snapshot Debugger
> * 设置快照点，以及查看快照
> * 设置记录点

## <a name="prerequisites"></a>系统必备

* 快照调试程序的 Azure 虚拟机 (VM) 和 Azure 虚拟机规模集是仅适用于 Visual Studio 2019 Enterprise 或更高版本与**Azure 开发工作负荷**。 （可在“各个组件”选项卡的“调试和测试” > “Snapshot Debugger”下找到它。）

    如果尚未安装，安装[Visual Studio 2019 Enterprise](https://visualstudio.microsoft.com/vs/)。

* 快照集合是适用于以下的 Azure 虚拟机 Machines\Virtual 规模 web 应用：
  * 在 .NET Framework 4.6.1 或更高版本上运行的 ASP.NET 应用程序。
  * 在 Windows 中的 .Net Core 2.0 或更高版本上运行的 ASP.NET Core 应用程序。

## <a name="open-your-project-and-start-the-snapshot-debugger"></a>打开项目并启动 Snapshot Debugger

1. 打开要进行快照调试的项目。

    > [!IMPORTANT]
    > 您需要打开到快照调试*相同版本的源代码*，它发布到 Azure 虚拟 Machine\Virtual 机规模集服务。

1. 选择“调试”>“附加 Snapshot Debugger...”。选择 Azure 虚拟 Machine\Virtual 机规模集部署到你的 web 应用和 Azure 存储帐户，然后依次**附加**。

      ![从“调试”菜单启动 Snapshot Debugger](../debugger/media/snapshot-debug-menu-attach.png)

      ![选择 Azure 资源](../debugger/media/snapshot-select-azure-resource-vm.png) 

    > [!IMPORTANT]
    > 第一次为 VM 选择“附加 Snapshot Debugger”时，IIS 将自动重启。
    > 选择第一次**附加 Snapshot Debugger**虚拟机规模集，需要手动升级每个虚拟机规模集实例。

    “模块”的元数据最初不会被激活，导航到 Web 应用，“开始收集”按钮将会激活。 Visual Studio 现在处于快照调试模式下。

   ![快照调试模式](../debugger/media/snapshot-message.png)

    > [!NOTE]
    > Application Insights 站点扩展还支持快照调试。 如果遇到“站点扩展过期”错误消息，请参阅[快照调试的疑难解答提示和已知问题](../debugger/debug-live-azure-apps-troubleshooting.md)以获取升级详细信息。
    > VMSS 的用户时需要在其虚拟机规模集实例手动升级后首次连接 Snapshot Debugger。

   **模块**窗口显示 Azure 虚拟 Machine\Virtual 机规模集的所有模块已都加载时 (选择**调试 > Windows > 模块**要打开此窗口)。

   ![选中“模块”窗口](../debugger/media/snapshot-modules.png)

## <a name="set-a-snappoint"></a>设置快照点

1. 在代码编辑器中，单击你感兴趣的代码行旁边的左滚动条槽以设置快照点。 请确保它是你已知将执行的代码。

   ![设置快照点](../debugger/media/snapshot-set-snappoint.png)

1. 单击“开始收集”以打开快照点。

   ![开启快照点](../debugger/media/snapshot-start-collection.png)

    > [!TIP]
    > 查看快照时，不能执行步骤，但可以在代码中放置多个快照点以在不同代码行处跟进执行。 如果代码中有多个快照点，快照调试器可以确保对应的快照来自相同的最终用户会话。 即使有多个用户点击应用，快照调试器仍会执行此操作。

## <a name="take-a-snapshot"></a>获取快照

启用快照点后，它将在快照点所在的代码行执行时捕获快照。 此执行可能由服务器上的实际请求引起。 若要强制命中快照点，请转到网站的浏览器视图，并执行命中快照点所需的任何操作。

## <a name="inspect-snapshot-data"></a>检查快照数据

1. 命中快照点时，快照将出现在诊断工具窗口。 若要打开此窗口，请依次选择“调试”>“窗口”>“显示诊断工具”。

   ![打开快照点](../debugger/media/snapshot-diagsession-window.png)

1. 双击快照点，以在代码编辑器中打开快照。

   ![检查快照数据](../debugger/media/snapshot-inspect-data.png)

   在此视图中，可通过将鼠标悬停在变量上来查看数据提示；使用“局部变量”、“监视”和“调用堆栈”窗口；以及计算表达式。

    网站本身仍然是实时的，最终用户不会受到影响。 默认情况下，每个快照点只捕获一个快照：快照点在捕获快照后即关闭。 如果要在此快照点再捕获一个快照，可以通过单击“更新集合”来重新打开快照点。

还可以向应用添加更多快照点，并使用“更新集合”按钮将其启动。

**需要帮助？** 请参阅[疑难解答和已知问题](../debugger/debug-live-azure-apps-troubleshooting.md)和[快照调试常见问题解答](../debugger/debug-live-azure-apps-faq.md)页。

## <a name="set-a-conditional-snappoint"></a>设置条件性快照点

如果难以在应用中重新创建某一特定状态，请考虑使用条件性快照点是否会有所帮助。 条件性快照点可帮助避免在应用进入所需状态前获取快照，例如，变量具有你想要检查的特定值的情况。 可以使用表达式、筛选器或命中次数设置表达式。

#### <a name="to-create-a-conditional-snappoint"></a>创建条件性快照点

1. 右键单击快照点图标（空心球）并选择“设置”。

   ![选择“设置”](../debugger/media/snapshot-snappoint-settings.png)

1. 在“快照点设置”窗口中，键入一个表达式。

   ![键入表达式](../debugger/media/snapshot-snappoint-conditions.png)

   在上图中，仅在 `visitor.FirstName == "Dan"` 时为快照点拍摄快照。

## <a name="set-a-logpoint"></a>设置记录点

除了在点击快照点时拍摄快照，还可以配置快照点以记录消息（即创建记录点）。 无需重新部署应用即可设置记录点。 记录点通过虚拟方式执行，不会对正在运行的应用程序产生任何影响或副作用。

#### <a name="to-create-a-logpoint"></a>创建记录点

1. 右键单击快照点图标（蓝色六边形），然后选择“设置”。

1. 在“快照点设置”窗口中，选择“操作”。

    ![创建记录点](../debugger/media/snapshot-logpoint.png)

1. 在“消息”字段中，可以输入想要记录的新日志消息。 还可以将日志消息中的变量放在大括号中，从而计算它们的值。

    如果选择“发送到输出窗口”，则在点击记录点时，消息将出现在“诊断工具”窗口中。

    ![“诊断工具”窗口中的记录点数据](../debugger/media/snapshot-logpoint-output.png)

    如果选择“发送到应用程序日志”，则在点击记录点时，消息会出现在可以看到来自 `System.Diagnostics.Trace`（或 .NET Core 中的 `ILogger`）的消息的任何位置，例如 [App Insights](/azure/application-insights/app-insights-asp-net-trace-logs)。

## <a name="next-steps"></a>后续步骤

在本教程中，你已了解如何使用适用于 Azure 虚拟机和 Azure 虚拟机规模集的 Snapshot Debugger。 你可能想要阅读有关此功能的更多详细信息。

> [!div class="nextstepaction"]
> [快照调试常见问题解答](../debugger/debug-live-azure-apps-faq.md)