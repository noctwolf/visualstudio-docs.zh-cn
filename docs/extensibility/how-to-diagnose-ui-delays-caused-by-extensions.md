---
title: "Visual Studio 中诊断扩展 UI 延迟 |Microsoft 文档"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
author: PooyaZv
ms.author: pozandev
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dffc67e550cb57f9f089e180ff399f27c817d253
ms.sourcegitcommit: 39c525ec200c6c4ea94815567b3fad7ab14fb7b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-diagnose-ui-delays-caused-by-extensions"></a>如何： 诊断 UI 导致扩展的延迟

当 UI 变得不响应时，Visual Studio 将检查 UI 线程调用堆栈开头叶和致力于基。 如果 Visual Studio 确定调用堆栈帧，属于是已安装和启用扩展的一部分的模块，它会显示一条通知。

![UI 延迟 （响应） 通知](media/ui-delay-notification-in-vs.png)

此通知告诉用户 UI 延迟 （即在 UI 中停止响应） 可能已被扩展中代码的结果。 它还提供选项禁用扩展或将来的通知，该扩展的用户。

本文档介绍如何诊断扩展代码什么原因导致 UI 延迟通知。 

> [!NOTE]
> 不使用 Visual Studio 实验实例来诊断 UI 将延迟。 使用实验实例中，这意味着可能不显示 UI 延迟通知时，调用堆栈分析 UI 延迟通知所需的某些部分已经关闭。

诊断过程的概述如下所示：
1. 标识触发器方案。
2. 使用日志记录的活动，重新启动 VS。
3. 启动 ETW 跟踪。
4. 触发通知后，就会再次出现。
5. 停止 ETW 跟踪。
6. 检查活动日志以获取延迟 id。
7. 分析使用从步骤 6 的延迟 ID ETW 跟踪。

在以下部分中，我们将简单介绍更多详细信息中的以下步骤。

## <a name="identifying-the-trigger-scenario"></a>标识触发器方案

若要执行诊断 UI 延迟，首先需要确定哪些 （序列的操作） 将导致 Visual Studio 以显示通知。 这是为你能够更高版本启用日志记录与触发通知的顺序。

## <a name="restarting-vs-with-activity-logging-on"></a>重新启动 VS 与活动日志记录

Visual Studio 可以生成"活动日志"在调试问题时提供有用的信息。 若要打开 Visual Studio 中的日志记录的活动，请启动 Visual Studio`/log`命令行选项。 Visual Studio 将启动后，活动日志存储在以下位置：

```DOS
%APPDATA%\Microsoft\VisualStudio\<vs_instance_id>\ActivityLog.xml
```

若要了解有关如何查找你 VS 的详细信息实例 ID，请参阅[用于检测和管理 Visual Studio 实例工具](../install/tools-for-managing-visual-studio-instances.md)。 我们将更高版本使用此活动日志以了解有关 UI 将延迟和相关的通知的详细信息。

## <a name="starting-etw-tracing"></a>启动 ETW 跟踪

你可以使用[PerfView](https://github.com/Microsoft/perfview/)收集 ETW 跟踪。 PerfView 提供一个易于使用的界面，同时用于收集 ETW 跟踪和分析它。 使用以下命令来收集跟踪：

```DOS
Perfview.exe collect C:\trace.etl /BufferSizeMB=1024 -CircularMB:2048 -Merge:true -Providers:*Microsoft-VisualStudio:@StacksEnabled=true -NoV2Rundown /kernelEvents=default+FileIOInit+ContextSwitch+Dispatcher
```

这样，"Microsoft visual Studio"提供程序，后者是 Visual Studio 用于与 UI 延迟通知相关的事件的提供程序。 它还指定关键字的内核提供程序可以使用 PerfView 来生成"线程时间堆栈"视图。

## <a name="triggering-the-notification-to-appear-again"></a>触发再次显示通知

一旦 PerfView 启动跟踪集合，你可以使用的触发器操作顺序 （从步骤 1） 通知就会再次出现。 通知显示之后，你可以停止 PerfView 以处理并生成输出跟踪文件的跟踪集合。

## <a name="stopping-etw-tracing"></a>停止 ETW 跟踪

若要停止跟踪集合，只需使用`Stop collection`PerfView 窗口上的按钮。 在停止跟踪收集后，PerfView 将自动处理 ETW 事件，并生成输出跟踪文件。

## <a name="examining-the-activity-log-to-get-the-delay-id"></a>检查活动日志以获取延迟 ID

如前所述，你可以找到在活动日志`%APPDATA%\Microsoft\VisualStudio\<vs_instance_id>\ActivityLog.xml`。 每次 Visual Studio 会检测 UI 延迟的扩展，它将节点写入活动日志`UIDelayNotifications`作为源。 此节点包含有关 UI 延迟的信息的四个部分：

- UI 延迟 ID，在 VS 会话中唯一标识 UI 延迟的序列号
- 从开始到关闭唯一标识你的 Visual Studio 会话中的会话 ID
- 是否要为 UI 延迟中显示通知
- 可能导致 UI 延迟扩展

```xml
<entry>
  <record>271</record>
  <time>2018/02/03 12:02:52.867</time>
  <type>Information</type>
  <source>UIDelayNotifications</source>
  <description>A UI delay (Delay ID = 0) has been detected. (Session ID=16e49d4b-26c2-4247-ad1c-488edeb185e0; Blamed extension="UIDelayR2"; Notification shown? Yes.)</description>
</entry>
```

> [!NOTE]
> 并非所有 UI 将延迟都导致通知。 因此，应始终检查"通知所示？" 为了正确地标识正确的 UI 延迟的值。

活动日志中找到正确的 UI 延迟后，记下在节点中指定的 UI 延迟 ID。 将使用 ID 来查找下一步中相应的 ETW 事件。

## <a name="analyzing-the-etw-trace"></a>分析 ETW 跟踪

接下来，打开跟踪文件。 你可以执行此操作使用的相同实例的 PerfView 或通过启动新实例并在左上方的窗口为跟踪文件的位置设置当前的文件夹路径。

![在 Perfview 中设置的文件夹路径](media/perfview-set-path.png)

然后，在左窗格中选择的跟踪文件，并通过从右键单击或上下文菜单中选择打开打开它。

> [!NOTE]
> 默认情况下 PerfView 输出 Zip 存档。 当你打开 trace.zip 时，它将自动解压缩存档并打开跟踪。 你可以跳过此通过跟踪回收期间取消选中"Zip"框。 但是，如果你计划传输，并在不同计算机之间使用跟踪，我们强烈建议不要取消选中"Zip"复选框。 没有使用此选项的所需的 Pdb，Ngen 程序集将不带跟踪并因此从 Ngen 程序集的符号将解析目标计算机上。 (请参阅[这篇博客文章](https://blogs.msdn.microsoft.com/devops/2012/12/10/creating-ngen-pdbs-for-profiling-reports/)的 Pdb Ngen 程序集的详细信息。) 

可能需要几分钟时间 PerfView 处理和打开的跟踪。 打开跟踪后，在其下将出现的各种"视图"列表。

![PerfView 跟踪摘要视图](media/perfview-summary-view-events-selected.png)

我们将首先使用"事件"视图以获取 UI 延迟时间范围：

1. 通过选择在跟踪下的"事件"节点，然后从右键单击或上下文菜单中选择打开打开"事件"视图。
2. 选择"`Microsoft-VisualStudio/ExtensionUIUnresponsiveness`"的左窗格中。
3. 按 Enter

应用所选内容和全部`ExtensionUIUnresponsiveness`事件显示在右窗格中。

![在事件视图中选择事件](media/perfview-event-selection.png)

在右窗格中的每个行都对应于 UI 延迟。 事件都包含一个"延迟 ID"值，该值应与步骤 6 中的活动日志中的延迟 ID 相匹配。 由于`ExtensionUIUnresponsiveness`激发 UI 延迟，事件的时间戳的末尾 （大约） 标记的 UI 延迟的结束时间。 此事件还包含延迟的持续时间。 我们可以将从用于 UI 延迟启动时获取的时间戳的结束时间戳的时间相减。

![计算 UI 延迟时间范围](media/ui-delay-time-range.png)

在上面的屏幕快照，例如，事件的时间戳是 12,125.679 还是延迟持续时间 6,143.085 （毫秒）。 因此，
* 延迟开始是 12,125.679 6,143.085 = 5,982.594。
* UI 延迟时间范围是 5,982.594 到 12,125.679。

一旦我们有时间范围，我们可以关闭超出了事件视图并打开"线程 （与 StartStop 活动） 的时间堆栈"视图。 此视图是尤其有用，因为其他线程或 O 绑定操作只在等待通常会阻止 UI 线程的扩展。 因此，"CPU 堆栈"视图，它是用于大多数情况下的转到选项，可能不会捕获线程所用阻止由于它不在该时间段使用 CPU 的时间。 "线程时间堆栈"按正确显示阻止时间可解决此问题。

![PerfView 摘要视图中的线程 （与 StartStop 活动） 的时间堆栈节点](media/perfview-thread-time-with-startstop-activities-stacks.png)

打开"线程时间堆栈"时视图中，选择"devenv"进程开始分析。

![线程进行 UI 延迟分析的时间堆栈视图](media/ui-delay-thread-time-stacks.png)

在"时间堆栈线程"视图中，在左上方的页上，你可以设置时间范围为我们计算到上一步中按 enter 键以便堆栈调整为该时间范围的值。

> [!NOTE]
> 确定哪个线程 UI （启动后） 线程可以是已打开 Visual Studio 后，已启动跟踪集合的情况下不够直观。 但是，UI （启动后） 线程的堆栈上的第一个元素是最可能始终操作系统 Dll （ntdll.dll 和 kernel32.dll） 跟 devenv ！？ 然后 msenv ！？。 此序列可帮助标识 UI 线程。

 ![标识启动线程](media/ui-delay-startup-thread.png)

你可以通过仅包括包含从你的包的模块的堆栈还进一步筛选此视图。

* 将"GroupPats"设置为要删除按默认添加任何分组的空文本。
* 组"IncPats"来包括除了现有进程筛选器程序集名称的一部分。 在这种情况下，它应为"devenv;UIDelayR2"。

![在线程时间堆栈视图中设置 GroupPath 和 IncPath](media/perfview-tts-group-path-inc-path.png)

PerfView 详细介绍了可用于确定你的代码中的性能瓶颈的帮助菜单下的指南。 此外，以下链接提供有关如何使用线程处理 Api 来优化你的代码的 Visual Studio 的详细信息：

* [https://aka.ms/vsthreading](https://aka.ms/vsthreading)
* [https://aka.ms/vsthreadingcookbook](https://aka.ms/vsthreadingcookbook)

> [!NOTE]
> 如果无法解决由于存在依赖关系不响应问题不具有控制通过 (例如如果你的扩展必须在 UI 线程上调用同步 VS 服务)，我们想要知道该情况。 如果你是我们的 Visual Studio 合作伙伴计划的成员，你可以通过提交开发人员支持请求请与我们联系。 否则，请使用报告问题工具以提交你的反馈，并包括`"Extension UI Delay Notifications"`标题中。 请还包括分析的详细的说明。
