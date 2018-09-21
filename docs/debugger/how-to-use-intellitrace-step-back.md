---
title: 查看快照使用 IntelliTrace 后退
ms.description: Learn how to take snapshots, and view snapshots with IntelliTrace step-back
ms.custom: mvc
ms.date: 09/19/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
ms.assetid: 7c60d929-d993-49dc-9db3-43b30be9912b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a0422237855a4332761eb50761e88df26ba639b2
ms.sourcegitcommit: 9765b3fcf89375ca499afd9fc42cf4645b66a8a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2018
ms.locfileid: "46495748"
---
# <a name="view-snapshots-using-intellitrace-step-back-in-visual-studio"></a>在 Visual Studio 中使用 IntelliTrace 后退查看快照

IntelliTrace 后退自动拍摄快照的应用程序的每个断点和调试程序单步执行事件。 凭借记录的快照便可以返回到上一个断点或步骤，并查看当时应用程序的状态。 如果希望查看以前的应用程序状态，但不想重新启动调试或重新创建所需应用状态，使用 IntelliTrace 后退可以节省时间。

IntelliTrace 后退可以开始于 Visual Studio Enterprise 2017 版本 15.5 和更高版本，并且需要 Windows 10 周年更新或更高版本。 调试 ASP.NET、 WinForms、 WPF、 托管的控制台应用程序和托管的类库当前支持的功能。 从 Visual Studio 2017 Enterprise 版本 15.7 开始，该功能还支持 ASP.NET Core 和.NET Core。 开始使用 Visual Studio 2017 Enterprise 15.9 版预览版 2，该功能还支持面向 Windows 的本机应用。 当前不支持调试 UWP 应用程序。

在本教程中，你将：

> [!div class="checklist"]
> * 启用 Intellitrace 事件和快照
> * 导航事件使用后退和步骤转发命令
> * 查看事件快照
  
## <a name="enable-intellitrace-events-and-snapshots-mode"></a>启用 IntelliTrace 事件和快照模式 

1. 在 Visual Studio Enterprise 中打开你的项目。

1. 打开**工具** > **选项** > **IntelliTrace**设置，然后选择选项**IntelliTrace 事件和快照**. 

    开始在 Visual Studio 2017 Enterprise 15.9 版预览版 2 中，此选项是**IntelliTrace 快照 （托管和本机）**。 

    ![启用 IntelliTrace 事件和快照模式](../debugger/media/intellitrace-enable-snapshots.png "启用 IntelliTrace 事件和快照模式")

1. 如果你想要在异常配置选项查看快照，请选择**IntelliTrace** > **高级**从**选项**对话框。

    这些选项是从 Visual Studio 2017 Enterprise 版本 15.7 中开始提供。

    ![在异常配置的快照的行为](../debugger/media/intellitrace-enable-snapshots-on-exceptions.png)

    启用事件和快照时，拍摄快照的异常上也默认启用。 您可以通过取消选择禁用异常的快照**异常事件时收集快照**。 启用此功能后，可为未经处理的异常拍摄快照。 为已处理的异常，才会引发异常并不是重新引发之前曾引发的异常拍摄快照。 通过从下拉列表中选择一个值，可以在异常上设置的最大快照数。 最大值适用于每次你的应用进入中断模式下 （例如您的应用程序达到断点时）。

    > [!NOTE]
    > 拍摄快照仅为异常事件 IntelliTrace 记录的。 对于托管代码中，可以指定 IntelliTrace 记录哪些事件，通过选择**工具** > **选项** > **IntelliTrace 事件**。

1. 在项目中，设置一个或多个断点并开始调试 (按**F5**)，或通过逐句通过代码启动调试 (**F10**或**F11**)。

    IntelliTrace 将在每个调试程序步骤中，断点事件和未经处理的异常事件的应用程序的进程的快照。 在中记录这些事件**事件**选项卡**诊断工具**窗口中的，与其他 IntelliTrace 事件。 若要打开此窗口，请选择**调试** > **Windows** > **显示诊断工具**。

    才提供快照在事件旁边会显示一个照相机图标。 

    ![事件选项卡上使用快照](../debugger/media/intellitrace-events-tab-with-snapshots.png "事件选项卡上的断点和步骤的快照")

    出于性能原因，非常快速地单步时不拍摄快照。 如果该步骤旁显示没有照相机图标，请尝试单步执行速度更慢。

## <a name="navigate-and-view-snapshots"></a>浏览和查看快照

1. 通过使用事件之间浏览**后退 （Alt + [）** 并**单步前进 (Alt +])** 中调试工具栏按钮。

    这些按钮导航中显示的事件**事件**选项卡**诊断工具窗口**。 单步执行后退或前进到某个事件会自动激活[历史调试](../debugger/historical-debugging.md)所选事件。

    ![向后移动和向前按钮](../debugger/media/intellitrace-step-back-icons-description.png "后退一步和前进按钮")

    当单步后退或前进时，Visual Studio 将进入历史调试模式。 在此模式下，调试器的上下文切换到所选的事件记录时的时间。 Visual Studio 还将指针移到相应的源窗口中的代码行。 

    从此视图中，您可以检查中的值**调用堆栈**，**局部变量**，**自动**，以及**监视**windows。 您还可以悬停以查看数据提示并执行中的表达式求值的变量**即时**窗口。 您看到的数据是进程的从应用程序在某个时间点拍摄的快照。

    因此，举例来说，如果已命中断点并且执行一个步骤 (**F10**)，则**后退一步**按钮可使 Visual Studio 中的对应于断点的代码行上的历史模式。 

    ![有关快照事件激活历史模式](../debugger/media/intellitrace-historical-mode-with-snapshot.png "正在激活历史模式下使用快照执行事件")

2. 若要返回到实时执行，请选择**继续 (F5)** 或单击**返回实时调试**信息栏中的链接。 

3. 你还可以查看从快照**事件**选项卡。若要执行此操作，选择一个事件，使用快照，然后单击**激活历史调试**。

    ![上一个事件激活历史调试](../debugger/media/intellitrace-activate-historical-debugging.png "事件激活历史调试")

    与不同**设置下一语句**命令，查看快照不会重新运行你的代码; 它为您提供了应用程序状态的静态视图的某个位置发生在过去的时间。

    ![概述 IntelliTrace 后退](../debugger/media/intellitrace-step-back-overview.png "概述的 IntelliTrace 后退")

    若要了解有关如何检查 Visual Studio 中的变量的详细信息，请参阅[调试器功能简介](../debugger/debugger-feature-tour.md)  

## <a name="frequently-asked-questions"></a>常见问题

#### <a name="how-is-intellitrace-step-back-different-from-intellitrace-events-only-mode"></a>不同于 IntelliTrace 事件的唯一模式是 IntelliTrace 后退什么？

IntelliTrace 事件的唯一模式允许您进行激活历史调试对调试器步骤和断点。 但是，IntelliTrace 只捕获中的数据**局部变量**并**自动**windows 如果 windows 已打开，并且它仅捕获已展开的数据和视图中。 在事件仅模式下，您通常没有变量和复杂对象的完整视图。 此外，表达式评估并查看数据在**监视**窗口不受支持。 

在事件和快照模式下，IntelliTrace 捕获应用程序的进程，包括复杂对象的整个快照。 在代码行，您可以看到相同的信息，如同已在断点处停止，（并且是否之前已展开的信息不重要）。 查看快照时，还支持表达式计算。  

#### <a name="what-is-the-performance-impact-of-this-feature"></a>什么是此功能的性能影响？ 

对单步执行的总体性能的影响取决于你的应用程序。 拍摄快照的开销为大约 30 毫秒。 时拍摄快照，分叉应用的过程，并且分支的副本会挂起。 当您查看快照时，Visual Studio 附加到进程的分支的副本。 对于每个快照，Visual Studio 复制仅页表，并设置为写入时复制的页。 如果堆上的对象更改与关联的快照调试程序步骤之间，相应的页表被然后复制，从而最小内存成本。 如果 Visual Studio 检测到没有足够的内存来拍摄快照时，它不会之一。
 
## <a name="known-issues"></a>已知问题  
* 如果使用 IntelliTrace 事件和快照模式下的早于 Windows 10 Fall Creators Update (RS3) 的 Windows 版本上，并且如果应用程序的调试平台目标设置为 x86，IntelliTrace 不拍摄快照。

    解决方法：
    * 安装或升级到 Windows 10 Fall Creators Update (RS3)。 
    * 或者： 
        1. 用 Visual Studio 安装程序安装用于桌面的 VC++ 2015.3 v140 工具集组件 (x86, x64)。
        2. 生成目标应用程序。
        3. 从命令行中，使用 editbin 工具设置`Largeaddressaware`目标可执行文件的标志。 例如，在 （更新后的路径） 可能会使用此命令:"C:\Program Files (x86) \Microsoft Visual Studio\Preview\Enterprise\VC\Tools\MSVC\14.12.25718\bin\Hostx86\x86\editbin.exe"/Largeaddressaware"C:\Path\To\Application\app.exe"。
        4. 若要启用调试，请按 F5。 现在，对调试器步骤和断点拍摄快照。

        > [!Note]
        > `Largeaddressaware`标志必须设置每个使用更改重新生成可执行文件的时间。

* 使用持久化的内存映射文件的应用程序上创建应用程序的进程的快照时, 的快照进程保留上内存映射文件的排他锁，（即使父进程已发布其锁）。 其他进程将仍然能够读取，但未写入到内存映射文件。

    解决方法：
    * 通过结束调试会话，请清除所有快照。 

* 其过程具有大量唯一内存区域，例如加载的 Dll，大量的应用程序的应用程序进行调试时逐句通过快照启用的性能可能会影响。 将在 Windows 的未来版本中解决此问题。 如果您遇到此问题，通过向我们stepback@microsoft.com。 

* 保存的文件时**调试 > IntelliTrace > 保存 IntelliTrace 会话**在事件和快照模式下，从快照中捕获的其他数据不可用的.itrace 文件中。 断点并单步事件，您将看到相同的信息，如同已在 IntelliTrace 事件仅模式下保存文件。 

## <a name="next-steps"></a>后续步骤

在本教程中，已学习了如何使用 IntelliTrace 后退。 您可能想要了解有关 IntelliTrace 的其他功能的详细信息。

> [!div class="nextstepaction"]
> [IntelliTrace 功能](../debugger/intellitrace-features.md)
