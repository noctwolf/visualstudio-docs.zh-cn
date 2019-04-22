---
title: 快照调试疑难解答 | Microsoft Docs
ms.custom: seodec18
ms.date: 11/07/2018
ms.topic: troubleshooting
helpviewer_keywords:
- debugger
ms.assetid: 511a0697-c68a-4988-9e29-8d0166ca044a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7b7916cbd3a7faa633baf53a18686779dc2b386c
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58857757"
---
# <a name="troubleshooting-and-known-issues-for-snapshot-debugging-in-visual-studio"></a>Visual Studio 中的快照调试疑难解答和已知问题

如果本文中所述的步骤未能解决你的问题，请向以下地址发送电子邮件：snaphelp@microsoft.com。

## <a name="issue-snappoint-does-not-turn-on"></a>问题：吸附点不会启用

如果你的快照点带有警告图标 ![快照点警告图标](../debugger/media/snapshot-troubleshooting-snappoint-warning-icon.png "快照点警告图标")，而不是常规快照点图标，则表示快照点未启用。

![快照点未启用](../debugger/media/snapshot-troubleshooting-dont-turn-on.png "快照点未开启")

执行以下步骤：

1. 确保生成和部署 app.isua1 时使用的是相同版本的源代码。 确保为你的部署加载了正确的符号。 为此，请在快照调试时查看“模块”窗口并验证“符号文件”列是否显示为调试的模块加载的 .pdb 文件。 Snapshot Debugger 将尝试自动下载符号并将其用于你的部署。

## <a name="issue-symbols-do-not-load-when-i-open-a-snapshot"></a>问题：我打开的快照时不加载符号

如果你看到以下窗口，则表示符号未加载。

![未加载符号](../debugger/media/snapshot-troubleshooting-symbols-wont-load.png "未加载符号")

执行以下步骤：

- 单击此页上的“更改符号设置...” 链接。 在“调试”>“符号”设置中，添加符号缓存目录。 设置符号路径后，重启快照调试。

   项目中可用的符号或 .pdb 文件必须与应用服务部署匹配。 大多数部署（通过 Visual Studio、使用 Azure Pipelines 的 CI/CD 或 Kudu 等进行的部署）会将你的符号文件一起发布到应用服务。 通过设置符号缓存目录，Visual Studio 可以使用这些符号。

   ![符号设置](../debugger/media/snapshot-troubleshooting-symbol-settings.png "符号设置")

- 或者，如果你的组织使用符号服务器或将符号置于不同的路径，请使用符号设置为你的部署加载正确的符号。

## <a name="issue-i-cannot-see-the-attach-snapshot-debugger-option-in-the-cloud-explorer"></a>问题：看不到云资源管理器中的"附加快照调试器"选项

执行以下步骤：

- 确保安装了 Snapshot Debugger 组件。 打开 Visual Studio 安装程序，然后选中 Azure 工作负载中的“Snapshot Debugger”组件。
::: moniker range="< vs-2019"
- 确保你的应用受支持。 目前，仅支持部署到 Azure 应用服务的 ASP.NET（4.6.1 及更高版本）和 ASP.NET Core（2.0及更高版本）应用。
::: moniker-end
::: moniker range=">= vs-2019"
- 确保你的应用受支持：
  - Azure 应用服务 - 在 .NET Framework 4.6.1 或更高版本上运行的 ASP.NET 应用程序。
  - Azure 应用服务 - 在 Windows 中的 .Net Core 2.0 或更高版本上运行的 ASP.NET Core 应用程序。
  - Azure 虚拟机（以及虚拟机规模集）- 在 .NET Framework 4.6.1 或更高版本上运行的 ASP.NET 应用程序。
  - Azure 虚拟机（以及虚拟机规模集）- 在 Windows 中的 .Net Core 2.0 或更高版本上运行的 ASP.NET Core 应用程序。
  - Azure Kubernetes 服务 - 在 Debian 9 中的 .Net Core 2.2 或更高版本上运行的 ASP.NET Core 应用程序。
  - Azure Kubernetes 服务 - 在 Alpine 3.8 中的 .Net Core 2.2 或更高版本上运行的 ASP.NET Core 应用程序。
  - Azure Kubernetes 服务 - 在 Ubuntu 18.04 中的 .Net Core 2.2 或更高版本上运行的 ASP.NET Core 应用程序。
::: moniker-end

## <a name="issue-i-only-see-throttled-snapshots-in-the-diagnostic-tools"></a>问题：我只看到限制在诊断工具的快照

![已阻止的快照点](../debugger/media/snapshot-troubleshooting-throttled-snapshots.png "已阻止的快照点")

执行以下步骤：

- 快照占用很少的内存，但确实存在内存使用。 如果 Snapshot Debugger 检测到服务器的内存负载过大，则不会创建快照。 可以通过停止 Snapshot Debugger 会话来删除已捕获的快照，然后重试。

## <a name="issue-snapshot-debugging-with-multiple-versions-of-the-visual-studio-gives-me-errors"></a>问题：快照调试与多个版本的 Visual Studio 为我提供的错误

VS 2019 需要在 Azure 应用服务上安装较新版本的 Snapshot Debugger 站点扩展。  此版本与 VS 2017 所用的旧版 Snapshot Debugger 站点扩展不兼容。  如果尝试将 VS 2019 中的 Snapshot Debugger 附加到之前已由 VS 2017 中的 Snapshot Debugger 进行调试的 Azure 应用服务，将收到以下错误：

![不兼容的 Snapshot Debugger 站点扩展 VS 2019](../debugger/media/snapshot-troubleshooting-incompatible-vs2019.png "不兼容的 Snapshot Debugger 站点扩展 VS 2019")

相反，如果使用 VS 2017 将 Snapshot Debugger 附加到之前已由 VS 2019 中的 Snapshot Debugger 进行调试的 Azure 应用服务，将收到以下错误：

![不兼容的 Snapshot Debugger 站点扩展 VS 2017](../debugger/media/snapshot-troubleshooting-incompatible-vs2017.png "不兼容的 Snapshot Debugger 站点扩展 VS 2017")

若要解决此问题，请在 Azure 门户中删除以下应用设置，并再次附加 Snapshot Debugger：

- INSTRUMENTATIONENGINE_EXTENSION_VERSION
- SNAPSHOTDEBUGGER_EXTENSION_VERSION

## <a name="issue-i-am-having-problems-snapshot-debugging-and-i-need-to-enable-more-logging"></a>问题：遇到快照调试的问题，我需要启用详细日志记录

### <a name="enable-agent-logs"></a>启用代理日志

若要启用和禁用代理日志记录，请打开 Visual Studio 并导航到“工具”>“选项”>“Snapshot Debugger”>“启用代理日志记录”。 请注意，如果同时还启用了“在会话启动时删除旧的代理日志”，则每次成功的 Visual Studio 附加都会删除以前的代理日志。

可以在以下位置找到代理日志：

- 应用服务：
  - 导航到应用服务的 Kudu 站点（即，yourappservice.scm.azurewebsites.net）并导航到调试控制台。
  - 代理日志存储在以下目录：D:\home\LogFiles\SiteExtensions\DiagnosticsAgentLogs\
- VM/VMSS：
  - 登录到你的 VM，代理日志存储，如下所示：C:\WindowsAzure\Logs\Plugins\Microsoft.Azure.Diagnostics.IaaSDiagnostics\<Version>\SnapshotDebuggerAgent_*.txt
- AKS
  - 导航到以下目录：/tmp/diag/AgentLogs/*

### <a name="enable-profilerinstrumentation-logs"></a>启用 Profiler/检测日志

可以在以下位置找到检测日志：

- 应用服务：
  - 错误日志记录将自动发送到 D:\Home\LogFiles\eventlog.xml，事件标记为 <<提供程序名称="检测引擎" //>> 或“生产断点”
- VM/VMSS：
  - 登录到 VM 并打开事件查看器。
  - 打开以下视图：*Windows 日志 > 应用程序*。
  - 使用生产断点或检测引擎按事件源筛选当前日志。
- AKS
  - 检测引擎日志记录路径如下：/tmp/diag/log.txt（在 DockerFile 中设置 MicrosoftInstrumentationEngine_FileLogPath）
  - 生产断点日志记录路径如下：/tmp/diag/shLog.txt

## <a name="known-issues"></a>已知问题

- 当前不支持使用多个 Visual Studio 客户端对同一个应用服务进行快照调试。
- ASP.NET Core 项目不完全支持 Roslyn IL 优化。 对于部分 ASP.NET Core 项目，你可能无法看到某些变量，或者无法在条件语句中使用某些变量。
- 无法在 ASP.NET Core 项目的条件语句或记录点中计算特殊变量（如 $FUNCTION 或 $CALLER）。
- 快照调试不适用于已启用[本地缓存](/azure/app-service/app-service-local-cache)的应用服务。
- 目前不支持快照调试 API 应用。

## <a name="site-extension-upgrade"></a>站点扩展升级

快照调试和 Application Insights 依赖于 ICorProfiler，该工具会加载到站点过程并在升级过程中导致文件锁定问题。 我们建议使用此过程来确保生产站点不会出现任何停机时间。

- 在应用服务中创建[部署槽位](/azure/app-service/web-sites-staged-publishing)并将你的站点部署到槽。
- 从 Visual Studio 中的 Cloud Explorer 或从 Azure 门户交换生产槽。
- 停止槽站点。 这将需要几秒钟来终止所有实例的站点 w3wp.exe 进程。
- 从 Kudu 站点或 Azure 门户升级槽站点扩展（“应用服务边栏选项卡”>“开发工具”>“扩展”>“更新”）。
- 启动槽站点。 建议访问该站点以再次将其预热。
- 交换生产槽。

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中进行调试](../debugger/index.md)
- [使用快照调试器调试实时 ASP.NET 应用](../debugger/debug-live-azure-applications.md)
- [调试实时 ASP.NET Azure 虚拟 Machines\Virtual 机规模集使用快照调试程序](../debugger/debug-live-azure-virtual-machines.md)
- [调试实时 ASP.NET Azure Kubernetes，使用快照调试程序](../debugger/debug-live-azure-kubernetes.md)
- [快照调试常见问题解答](../debugger/debug-live-azure-apps-faq.md)