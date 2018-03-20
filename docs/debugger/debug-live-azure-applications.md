---
title: "调试实时 ASP.NET Azure 应用程序的 Visual Studio |Microsoft 文档"
ms.description: Learn how to set snappoints and view snapshots with the Snapshot Debugger
ms.custom: mvc
ms.date: 03/16/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugger
ms.assetid: adb22512-4d4d-40e5-9564-1af421b7087e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- aspnet
- azure
ms.openlocfilehash: d313dea17700d4e64d3156ee72ee15521111329b
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2018
---
# <a name="debug-live-aspnet-azure-apps-using-the-snapshot-debugger"></a>调试使用快照调试器的实时 ASP.NET Azure 应用程序

你感兴趣的代码在执行时，快照调试器将会在生产应用的快照。 要指示调试程序拍摄快照，可在代码中设置 snappoints 和 logpoints。 使用调试程序，可精确查看出错的内容，而不影响生产应用程序的流量。 快照调试程序有助于大幅减少用于解决生产环境中发生的问题的时间。

Snappoints 以及 logpoints 都类似于断点，但与断点，不同 snappoints 不终止应用程序命中条件。 通常情况下，捕获在 snappoint 快照采用 10 20 毫秒。 

快照集合适用于在 Azure App Service 中运行的以下 Web 应用：

- 在 .NET Framework 4.6.1 或更高版本上运行的 ASP.NET 应用程序。
- 在 Windows 中的 .Net Core 2.0 或更高版本上运行的 ASP.NET Core 应用程序。

此外，快照调试器仅可用于 Visual Studio 2017 Enterprise 15.5 或更高版本和基本或更高版本的 App Service 计划。 

在本教程中，你将：

> [!div class="checklist"]
> * 启动快照调试器
> * 设置 snappoint 和查看快照
> * 设置 logpoint

## <a name="start-the-snapshot-debugger"></a>启动快照调试器

1. 安装[Visual Studio 2017 Enterprise 版本 15.5](https://www.visualstudio.com/downloads/)或更高版本。 如果你正在从以前的 Visual Studio 2017 安装更新，运行 Visual Studio 安装程序，并检查 ASP.NET 和 web 开发工作负荷中的快照调试器组件。

2. 打开你想要进行快照调试的项目。 

    > [!IMPORTANT] 
    > 到快照调试，需要打开**相同版本的源代码**，它发布到你的 Azure 应用程序服务。 

3. 在云资源管理器 (**视图 > 云资源管理器**)，右键单击你的项目部署到 Azure App Service，然后选择**附加快照调试器**。

   ![启动快照调试器](../debugger/media/snapshot-launch.png)

    你选择的第一个时间**附加快照调试器**，系统会提示你在你的 Azure App Service 上安装了快照调试器站点扩展。 此安装需要重新启动你的 Azure 应用程序服务。 

   Visual Studio 现在处于调试模式的快照。

    > [!NOTE]
    > Application Insights 站点扩展插件还支持快照调试。 如果你遇到的"站点扩展过期"错误消息，请参阅[故障排除提示和快照调试的已知的问题](../debugger/debug-live-azure-apps-troubleshooting.md)升级详细信息。

   ![快照调试模式](../debugger/media/snapshot-message.png)

   **模块**窗口显示你的所有模块已将时都加载 Azure App Service (选择**调试 / Windows / 模块**要打开此窗口)。

   ![检查模块窗口](../debugger/media/snapshot-modules.png)

## <a name="set-a-snappoint"></a>设置 snappoint

1. 在代码编辑器中，单击你感兴趣设置 snappoint 的代码行旁边的左滚动条槽。 请确保它是你知道将执行的代码。

   ![设置 snappoint](../debugger/media/snapshot-set-snappoint.png)

2. 单击**开始收集**开启 snappoint。  

   ![开启 snappoint](../debugger/media/snapshot-start-collection.png)

    > [!TIP]
    > 您不能逐句时查看快照，但你可以将多个 snappoints 放在你的代码以按照不同的代码行处的执行。 如果你在代码中有多个 snappoints，快照调试器可以确保相应快照从相同的最终用户会话。 即使有达到你的应用程序的多个用户，则快照调试器引发此异常。

## <a name="take-a-snapshot"></a>拍摄快照

启用 snappoint 后，它将捕获快照时的代码放置 snappoint 行执行。 此执行可能引起你的服务器上的实际请求。 若要强制你 snappoint 人命中，请转到您的网站的浏览器视图并采取任何操作所需导致要进行点击你 snappoint。

## <a name="inspect-snapshot-data"></a>检查快照数据

1. Snappoint 命中时，快照将显示在诊断工具窗口中。 若要打开此窗口，请选择**调试 / Windows / 显示诊断工具**。

   ![打开 snappoint](../debugger/media/snapshot-diagsession-window.png)

1. 双击 snappoint 以在代码编辑器中打开快照。

   ![检查快照数据](../debugger/media/snapshot-inspect-data.png)

   从此视图中，你可以将鼠标悬停在变量以查看数据提示，请使用**局部变量**，**观察**，和**调用堆栈**windows，并且还对表达式求值。

    网站本身，则仍实时并且不影响最终用户。 默认情况下捕获每 snappoint 只有一个快照： snappoint 捕获快照后关闭。 如果你想要捕获 snappoint 在另一个快照，你可以 snappoint 重新打开通过单击**更新集合**。

此外可以将多个 snappoints 添加到你的应用程序，并与将其打开**更新集合**按钮。

**需要帮助？** 请参阅[疑难解答和已知的问题](../debugger/debug-live-azure-apps-troubleshooting.md)和[适用的快照调试常见问题](../debugger/debug-live-azure-apps-faq.md)页。

## <a name="set-a-conditional-snappoint"></a>设置条件 snappoint

如果很难重新创建你的应用程序中的特定状态，请考虑是否可以帮助条件 snappoint 使用。 条件 snappoints 帮助您避免拍摄快照，直到应用进入期望的状态，例如在变量具有你想要检查特定值。 你可以设置条件使用表达式，筛选器，或命中次数。

#### <a name="to-create-a-conditional-snappoint"></a>若要创建条件 snappoint

1. 右键单击一个 snappoint 图标 （空心球） 并选择**设置**。

   ![选择设置](../debugger/media/snapshot-snappoint-settings.png)

1. 在 snappoint 设置窗口中，键入一个表达式。

   ![键入一个表达式](../debugger/media/snapshot-snappoint-conditions.png)

   在上图中，快照仅花费的 snappoint 时`visitor.FirstName == "Dan"`。

## <a name="set-a-logpoint"></a>设置 logpoint

除了命中 snappoint 时拍摄快照，你还可以配置 snappoint 来记录消息 （即，创建 logpoint）。 你可以设置 logpoints 而无需重新部署你的应用程序。 Logpoints 几乎执行，并且会导致没有影响或负面影响到你运行的应用程序。

#### <a name="to-create-a-logpoint"></a>若要创建 logpoint

1. 右键单击一个 snappoint 图标 （蓝色六边形） 并选择**设置**。

1. 在 snappoint 设置窗口中，选择**操作**。

    ![创建 logpoint](../debugger/media/snapshot-logpoint.png)

1. 在消息字段中，你可以输入你希望记录新的日志消息。 你还可以通过将它们放置在大括号内日志消息中评估变量。

    如果你选择**将发送到输出窗口**、 logpoint 命中时，在诊断工具窗口中显示的消息。

    ![Logpoint diagsession 窗口中的数据](../debugger/media/snapshot-logpoint-output.png)

    如果你选择**将发送到应用程序日志**、 logpoint 命中时，任何位置，你可以看到消息从显示的消息`System.Diagnostics.Trace`(或`ILogger`.NET 核心中)，如[App Insights](/azure/application-insights/app-insights-asp-net-trace-logs)。

## <a name="next-steps"></a>后续步骤

在本教程中，你已了解如何使用快照调试器。 你可能想要阅读有关此功能的更多详细信息。

> [!div class="nextstepaction"]
> [快照调试常见问题解答](../debugger/debug-live-azure-apps-faq.md)
