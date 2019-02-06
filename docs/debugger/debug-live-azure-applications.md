---
title: 调试实时 ASP.NET Azure 应用
description: 了解如何设置吸附点和查看快照调试程序的快照。
ms.custom: mvc
ms.date: 03/16/2018
ms.topic: conceptual
helpviewer_keywords:
- debugger
ms.assetid: adb22512-4d4d-40e5-9564-1af421b7087e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- aspnet
- azure
ms.openlocfilehash: f0936078039c4c1071f0214b61702a7f57f794ec
ms.sourcegitcommit: 0f7411c1a47d996907a028e920b73b53c2098c9f
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2019
ms.locfileid: "55690187"
---
# <a name="debug-live-aspnet-azure-apps-using-the-snapshot-debugger"></a>使用 Snapshot Debugger 调试实时 ASP.NET Azure 应用

Snapshot Debugger 会在你感兴趣的代码执行时为生产中的应用拍摄快照。 若要指示该调试器拍摄快照，可以在代码中设置快照点和记录点。 通过该调试器，可精确查看出错的内容，而不会影响生产应用程序的流量。 Snapshot Debugger 有助于大幅减少解决生产环境中出现的问题所需的时间。

快照点和记录点类似于断点，但与断点不同的是，快照点不会在命中时停止应用程序。 通常，在快照点捕获快照需要 10-20 毫秒。

在本教程中，你将：

> [!div class="checklist"]
> * 启动快照调试器
> * 设置快照点，以及查看快照
> * 设置记录点

## <a name="prerequisites"></a>系统必备

* 快照调试器功能仅适用于 Visual Studio 2017 Enterprise 版本 15.5 或更高版本与**Azure 开发工作负荷**。 (下**各个组件**选项卡上，您发现下**调试和测试** > **快照调试程序**。)

    如果尚未安装，安装[Visual Studio 2017 Enterprise 版本 15.5](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)或更高版本。 如果要从以前的 Visual Studio 2017 安装更新，运行 Visual Studio 安装程序并签入的快照调试器组件**ASP.NET 和 web 开发工作负荷**。

* 基本或更高版本的 Azure 应用服务计划。

* 快照集合适用于在 Azure App Service 中运行的以下 Web 应用：

    * 在 .NET Framework 4.6.1 或更高版本上运行的 ASP.NET 应用程序。
    * 在 Windows 中的 .Net Core 2.0 或更高版本上运行的 ASP.NET Core 应用程序。

## <a name="open-your-project-and-start-the-snapshot-debugger"></a>打开你的项目并启动快照调试器

1. 打开你想要快照调试的项目。

    > [!IMPORTANT]
    > 对于快照调试，需要打开与已发布到 Azure 应用服务的“相同版本的源代码”。

1. 在云资源管理器（“视图”>“云资源管理器”）中，右键单击项目部署到的 Azure 应用服务，然后选择“附加快照调试器”。

   ![启动快照调试程序](../debugger/media/snapshot-launch.png)

    第一次选择“附加快照调试器”时，系统会提示在 Azure 应用服务上安装快照调试器站点扩展。 此安装需要重启 Azure 应用服务。

   Visual Studio 现在处于快照调试模式下。

    > [!NOTE]
    > Application Insights 站点扩展还支持快照调试。 如果你遇到的"站点扩展已过期"错误消息，请参阅[故障排除提示和已知的问题的快照调试](../debugger/debug-live-azure-apps-troubleshooting.md)升级的详细信息。

   ![快照调试模式](../debugger/media/snapshot-message.png)

   “模块”窗口会显示何时已加载了 Azure 应用服务的所有模块（选择“调试”/“窗口”/“模块”可打开此窗口）。

   ![检查模块窗口](../debugger/media/snapshot-modules.png)

## <a name="set-a-snappoint"></a>设置快照点

1. 在代码编辑器中，单击你感兴趣的代码行旁边的左滚动条槽以设置快照点。 请确保它是你已知将执行的代码。

   ![设置快照点](../debugger/media/snapshot-set-snappoint.png)

2. 单击“开始收集”以打开快照点。

   ![开启快照点](../debugger/media/snapshot-start-collection.png)

    > [!TIP]
    > 查看快照时，不能执行步骤，但可以在代码中放置多个快照点以在不同代码行处跟进执行。 如果代码中有多个快照点，快照调试器可以确保对应的快照来自相同的最终用户会话。 即使有多个用户点击应用，快照调试器仍会执行此操作。

## <a name="take-a-snapshot"></a>获取快照

启用快照点后，它将在快照点所在的代码行执行时捕获快照。 此执行可能由服务器上的实际请求引起。 若要强制命中快照点，请转到网站的浏览器视图，并执行命中快照点所需的任何操作。

## <a name="inspect-snapshot-data"></a>检查快照数据

1. 命中快照点时，快照将出现在诊断工具窗口。 若要打开此窗口，请选择“调试”/“窗口”/“显示诊断工具”。

   ![打开快照点](../debugger/media/snapshot-diagsession-window.png)

1. 双击快照点，以在代码编辑器中打开快照。

   ![检查快照数据](../debugger/media/snapshot-inspect-data.png)

   在此视图中，可通过将鼠标悬停在变量上来查看数据提示；使用“局部变量”、“监视”和“调用堆栈”窗口；以及计算表达式。

    网站本身仍然是实时的，最终用户不会受到影响。 默认情况下，每个快照点只捕获一个快照：快照点在捕获快照后即关闭。 如果要在此快照点再捕获一个快照，可以通过单击“更新集合”来重新打开快照点。

还可以向应用添加更多快照点，并使用“更新集合”按钮将其启动。

**需要帮助？** 请参阅[疑难解答和已知的问题](../debugger/debug-live-azure-apps-troubleshooting.md)并[快照调试常见问题解答](../debugger/debug-live-azure-apps-faq.md)页。

## <a name="set-a-conditional-snappoint"></a>设置条件性快照点

如果难以在应用中重新创建某一特定状态，请考虑使用条件性快照点是否会有所帮助。 条件性快照点可帮助避免在应用进入所需状态前获取快照，例如，变量具有你想要检查的特定值的情况。 可以使用表达式、筛选器或命中次数设置表达式。

#### <a name="to-create-a-conditional-snappoint"></a>若要创建条件的吸附点

1. 右键单击吸附点图标 （空心球），然后选择**设置**。

   ![选择“设置”](../debugger/media/snapshot-snappoint-settings.png)

1. 在吸附点设置窗口中，键入一个表达式。

   ![键入一个表达式](../debugger/media/snapshot-snappoint-conditions.png)

   在上图中，仅拍摄快照的吸附点时`visitor.FirstName == "Dan"`。

## <a name="set-a-logpoint"></a>设置记录点

除了在命中吸附点时，拍摄快照，还可以配置吸附点将消息记录 （即，创建记录点）。 您可以设置个记录点，而无需重新部署您的应用程序。 记录点几乎执行，并会导致没有影响或负面影响到你正在运行的应用程序。

#### <a name="to-create-a-logpoint"></a>若要创建的记录点

1. 右键单击吸附点图标 （蓝色六边形），然后选择**设置**。

1. 在吸附点设置窗口中，选择**操作**。

    ![创建记录点](../debugger/media/snapshot-logpoint.png)

1. 在消息字段中，可以输入想要记录新的日志消息。 您也可以通过将它们放在大括号内将日志消息中计算变量。

    如果愿意**将发送到输出窗口**，当命中记录点，请在诊断工具窗口中将显示该消息。

    ![Diagsession 窗口中的记录点数据](../debugger/media/snapshot-logpoint-output.png)

    如果愿意**发送到应用程序日志**，当命中记录点，请任意位置，您可以看到消息从出现的消息`System.Diagnostics.Trace`(或`ILogger`.NET Core 中)，如[App Insights](/azure/application-insights/app-insights-asp-net-trace-logs)。

## <a name="next-steps"></a>后续步骤

在本教程中，已学习了如何使用快照调试程序。 您可能想要阅读有关此功能的更多详细信息。

> [!div class="nextstepaction"]
> [快照调试常见问题解答](../debugger/debug-live-azure-apps-faq.md)
