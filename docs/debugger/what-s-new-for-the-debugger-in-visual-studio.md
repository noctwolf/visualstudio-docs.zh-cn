---
title: "在 Visual Studio 2017 调试器的新增功能 |Microsoft 文档"
ms.custom: 
ms.date: 03/07/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, what's new
- what's new [debugger]
- debugging [Visual Studio], what's new
- what's new [Visual Studio], debugging
ms.assetid: 2aed9caa-2384-4e49-8595-82d8b06cf271
caps.latest.revision: "81"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8df1dcde73496f6ec8c25eb33cb4b6986a721f33
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="whats-new-for-the-debugger-in-includevsdev15miscincludesvsdev15mdmd"></a>在调试器的新增功能[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]

调试器包括以下新功能：

- 15.5 中的新增功能**快照调试器**你感兴趣的代码在执行时，获取你在生产应用的快照。 要指示调试程序拍摄快照，可在代码中设置 snappoints 和 logpoints。 使用调试程序，可精确查看出错的内容，而不影响生产应用程序的流量。 快照调试程序有助于大幅减少用于解决生产环境中发生的问题的时间。

    快照集合适用于在 Azure App Service 中运行的以下 Web 应用：

    * 在 .NET Framework 4.6.1 或更高版本上运行的 ASP.NET 应用程序。
    * 在 Windows 中的 .Net Core 2.0 或更高版本上运行的 ASP.NET Core 应用程序。

    有关详细信息，请参阅[调试实时 ASP.NET 应用程序使用快照调试器](../debugger/debug-live-azure-applications.md)。

- Visual Studio Enterprise 中 15.5 仅中的新增功能**IntelliTrace 步骤回**步骤事件也会自动编制的应用程序的每个断点和调试器的快照。 凭借记录的快照便可以返回到上一个断点或步骤，并查看当时应用程序的状态。 如果希望查看以前的应用程序状态，但不想重新启动调试或重新创建所需应用状态，使用 IntelliTrace 后退可以节省时间。

    可以通过使用调试工具栏中的“后退”和前进”按钮浏览和查看快照。 这些按钮用于浏览“诊断工具”窗口中“事件”选项卡上显示的事件。

    ![单步执行向后和向前按钮](../debugger/media/intellitrace-step-back-icons-description.png  "步骤向后和向前按钮")

    有关详细信息，请参阅[使用 IntelliTrace 后退查看快照](../debugger/how-to-use-intellitrace-step-back.md)页。

- **异常帮助器**替换异常助手并且会出现在非模式对话框中发生错误的位置。 **异常帮助器**提供快地访问任何内部异常，调试器使用 （如果可用），其他分析和立即访问**异常设置**异常。 也可以将异常帮助窗口拖动到浮点视图，如果它阻止你需要查看的内容。

    例如， **NullReferenceException**现在显示具有 null 引用 （额外信息） 的变量。

    ![调试器的异常帮助器](../debugger/media/dbg-exception-helper.png "DbgExceptionHelper")

    有关详细信息，请参阅 [Using the New Exception Helper in Visual Studio](https://blogs.msdn.microsoft.com/visualstudioalm/2016/03/31/using-the-new-exception-helper-in-visual-studio-15-preview/)（使用 Visual Studio 中的新异常帮助器）博客文章。

- 你现在可以运行到代码在暂停时在调试器中通过选择某一行**到此处运行执行**绿色箭头图标 （你将看到悬停在某个代码行时图标）。 这消除了需要设置临时断点。

    ![调试器的运行到单击](../debugger/media/dbg-run-to-click.png "DbgRunToClick") 

- 你可以设置条件中的异常上**异常设置**对话框 (可以执行此操作通过使用**编辑条件**异常设置对话框中或通过右键单击菜单上的图标异常。）当前支持的条件包括用于包含或排除异常的模块名称。

    ![关于异常的条件](../debugger/media/dbg-conditional-exception.png "DbgConditionalException")

- 附加到对话框中包括一个新的搜索功能，可帮助你更快速确定你需要将附加到进程的进程。

    ![中的搜索附加到进程](../debugger/media/dbg-attach-to-process-search.png "DbgAttachToProcessSearch") 

有关这些新功能的详细信息，请参阅[的发行说明[!include[vs_dev15](../misc/includes/vs_dev15_md.md)] ](https://www.visualstudio.com/en-us/news/releasenotes/vs2017-relnotes#debuggingdiag)。
  
## <a name="see-also"></a>请参阅  
 [在 Visual Studio 中进行调试](../debugger/index.md)  
 [调试器功能简介](../debugger/debugger-feature-tour.md)