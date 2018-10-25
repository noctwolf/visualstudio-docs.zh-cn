---
title: 调试多线程应用程序
description: 调试在 Visual Studio 中使用线程窗口和调试位置工具栏
ms.custom: ''
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- multithreaded debugging, tutorial
- tutorials, multithreaded debugging
ms.assetid: adfbe002-3d7b-42a9-b42a-5ac0903dfc25
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bcd3a3f47af8251f6f4bfa1b5b5f08da7a1f3e3e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49933555"
---
# <a name="walkthrough-debug-a-multithreaded-application-in-visual-studio-using-the-threads-window"></a>演练： 调试多线程应用程序在 Visual Studio 中使用线程窗口
Visual Studio 提供了**线程**窗口和其他用户界面元素，以帮助您调试多线程应用程序。 本教程演示如何使用**线程**窗口和**调试位置**工具栏。 有关其他工具的信息，请参阅[开始调试多线程应用程序](../debugger/get-started-debugging-multithreaded-apps.md)。 本教程中，只需要几分钟，但完成它将使您熟悉用于调试多线程应用程序的功能。   
  
若要开始学习本教程，需要一个多线程应用程序项目。 请按照下面列出的步骤创建该项目。  
  
#### <a name="to-create-the-multithreaded-app-project"></a>若要创建多线程应用程序项目  
  
1.  上**文件**菜单中，选择**新建**，然后单击**项目**。  
  
     此时将出现 “新建项目” 对话框。  
  
2.  在中**项目类型**s 框中，单击所选的语言： **Visual Basic**， **Visual C#**，或者**Visual c + +**。  
  
3.  下**Windows 桌面**，选择**控制台应用**。  
  
4.  在中**名称**框中，键入名称 MyThreadWalkthroughApp。  
  
5.  单击 **“确定”**。  
  
     新的控制台项目随即显示。 创建该项目后，将显示源文件。 根据所选的语言，源文件的名称可能是 Module1.vb、Program.cs 或 MyThreadWalkthroughApp.cpp  
  
6.  删除出现在源代码文件中的代码并替换该主题的"创建线程"的部分中显示的示例代码[创建线程并传递数据的开始时间](/dotnet/standard/threading/creating-threads-and-passing-data-at-start-time)。  
  
7.  在“文件”  菜单上，单击“全部保存” 。  
  
#### <a name="to-begin-the-tutorial"></a>若要开始学习教程  
  
-   在源代码编辑器中，查找以下代码：  
  
    ```VB  
    Thread.Sleep(3000)   
    Console.WriteLine()
    ```  
  
    ```csharp  
    Thread.Sleep(3000);  
    Console.WriteLine();  
    ```  
  
    ```C++  
    Thread::Sleep(3000);  
    Console.WriteLine();  
    ```  
  
#### <a name="to-start-debugging"></a>开始调试  
  
1. 单击左滚动条槽中`Console.WriteLine`语句将新断点。  
  
    在源代码编辑器左侧的滚动条槽，将显示一个红色圆圈。 这表示现在已在该位置设置了一个断点。  
  
2. 上**调试**菜单上，单击**开始调试**(**F5**)。  
  
    调试开始，您的控制台应用程序开始运行，随后在断点处停止。  
  
3. 如果此时控制台应用程序窗口具有焦点，请在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 窗口中单击以使焦点返回到 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]。  
  
4. 在源代码编辑器中，找到包含以下代码行：  
  
   ```VB  
   Thread.Sleep(5000)   
   ```  
  
   ```csharp  
   Thread.Sleep(3000);  
   ```  
  
   ```C++  
   Thread::Sleep(3000);  
   ```
  
#### <a name="to-discover-the-thread-marker"></a>发现线程标记  

1.  在调试工具栏中，单击**源中显示线程**按钮![在源中显示线程](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker")。 
  
2.  查看窗口左侧的滚动条槽。 在此行中，你会看到*线程标记*图标![线程标记](../debugger/media/dbg-thread-marker.png "ThreadMarker") ，类似于两根细线。 线程标记指示线程在此位置停止。  
  
3.  将指针悬停在线程标记上。 屏幕上显示数据提示。 数据提示将告诉您每个已停止线程的名称和线程 ID 号。 在此情况下，只有一个线程，其名称可能是 `<noname>`。  

    > [!TIP]
    > 您可能会发现通过重命名它们识别无名称线程很有帮助。 在线程窗口中，选择**重命名**上右键单击后**名称**线程行中的列。
  
4.  右键单击要查看的快捷菜单上的可用选项的线程标记。 
    
  
## <a name="flagging-and-unflagging-threads"></a>标记线程和取消标记线程  
可以标记要格外关注的线程。 标记线程是一个好的方法来跟踪重要线程并忽略您不关心的线程。  
  
#### <a name="to-flag-threads"></a>标记线程   

1.  上**视图**菜单，依次指向**工具栏**。  
  
    请确保**调试位置**选中工具栏。

2.  转到**调试位置**工具栏，然后单击**线程**列表。  
  
    > [!NOTE]
    >  可以通过三个突出显示的列表来识别此工具栏：**进程**，**线程**，并**堆栈帧**。  
  
3.  请注意列表中显示的线程数目。  
  
4.  返回在源代码编辑器，并右击线程标记![线程标记](../debugger/media/dbg-thread-marker.png "ThreadMarker")试。  
  
5.  在快捷菜单上，指向**标志**，然后单击线程名称和 ID 号。  
  
6.  返回到**调试位置**工具栏和查找**仅显示标记的线程**图标![显示已标记线程](../debugger/media/dbg-threads-show-flagged.png "ThreadMarker")到角**线程**列表。  
  
    在按钮上的标志图标之前灰显。 现在，它是活动的按钮。  
  
7.  单击**仅显示标记的线程**图标。  
  
    现在只有标记的线程显示在该列表中。 (可以单击单个标记按钮切换回**显示所有线程**模式。)

8. 线程窗口打开，请选择**调试 > Windows > 线程**。

    ![线程窗口](../debugger/media/dbg-threads-window.png "ThreadsWindow")  
  
    在中**线程**窗口中，标记的线程具有附加到它的突出显示的红色标记图标。

    > [!TIP]
    > 当你具有标记的一些线程时，可以右键单击代码编辑器中的代码行，然后选择**运行到光标处的已标记线程**（请确保选择所有标记的线程的代码将访问）。 这将中止线程，从而使其变得更容易控制的执行顺序代码的选定行上[冻结和解冻线程](#bkmk_freeze)。
  
11. 在源代码编辑器中，再次右键单击线程标记。  
  
     请注意此时快捷菜单上提供的选项。 而不是**标志**，现在你会看到**取消标记**。 不要单击**取消标记**。  

     若要了解如何取消标记线程，请转到下一步的过程。  
  
#### <a name="to-unflag-threads"></a>取消标记线程  
  
1.  在中**线程**窗口中，右键单击标记的线程与对应的行。  
  
     一个快捷菜单随即显示。 其中包括选项**取消标记**并**取消标记所有线程**。  
  
2.  若要取消标记线程，请单击**取消标记**。  

    看看**调试位置**再次工具栏。 **仅显示标记的线程**按钮再次灰显。 这是因为您已取消标记唯一的已标记线程。 由于没有已标记的线程，工具栏已将返回到**显示所有线程**模式。 单击**线程**列出并验证是否可以看到所有线程。  
  
5.  返回到**线程**窗口，并检查信息列。  
  
    在第一个专栏中，会注意到线程列表的每一行中的标志大纲图标。 （概要意味着线程已取消标记。）  
  
6.  单击两个线程，第二个和第三，从列表底部的标志大纲图标。 

    标记图标变为纯红色，而非空心边框。  
  
7.  单击该标记列顶部的按钮。  
  
    单击该按钮时，线程列表的顺序将会改变。 此时，线程列表的排序形式为标记的线程位于顶部。  
  
8.  再次单击该标记列顶部的按钮。  
  
    排序顺序再次改变。  
  
## <a name="more-about-the-threads-window"></a>有关“线程”窗口的更多信息  
  
#### <a name="to-learn-more-about-the-threads-window"></a>了解有关“线程”窗口的更多信息  
  
1.  在中**线程**窗口中，检查从左侧的第三个列。 在此列顶部的按钮**ID**。  
  
2.  单击**ID**。  
  
     此时，线程列表按照线程 ID 号排序。  
  
3.  右击列表中的任意线程。 在快捷菜单上，单击**十六进制显示**。  
  
     线程 ID 号的格式将会改变。  
  
4.  将鼠标指针悬停**位置**列列表中的任何线程。  
  
     经过短暂的延迟后，将会出现数据提示。 其中显示线程的部分调用堆栈。

     > [!TIP]
     > 有关线程的调用堆栈的图形视图，打开[并行堆栈](../debugger/using-the-parallel-stacks-window.md)窗口 (调试时，选择**调试 / Windows / 并行堆栈**)。  
  
5.  查看第四个列，从标记为左**类别**。 线程按类别分类。  
  
     进程中创建的第一个线程称为主线程。 请在线程列表中找到它。  
  
6.  右击主线程，然后单击**切换到线程**。  
  
     一个**中断模式**窗口会显示。 它指示调试器当前正在不执行任何代码，它可以显示 （因为它是主线程）。   
  
7.  看看**调用堆栈**窗口和**调试位置**工具栏。  
  
     内容**调用堆栈**窗口已更改。 

## <a name="bkmk_freeze"></a> 冻结和解冻线程执行 

您可以冻结和解冻 （暂停和恢复） 线程来控制线程在其中执行工作的顺序。 这可以帮助你解决并发问题，例如死锁和争用条件。

> [!TIP]
> 如果你想要操作一个线程，并且不冻结其他线程 （也一种常见调试方案），请参阅[开始调试多线程应用程序](../debugger/get-started-debugging-multithreaded-apps.md#bkmk_follow_a_thread)。
  
#### <a name="to-freeze-and-unfreeze-threads"></a>冻结和解冻线程  
  
1.  在中**线程**窗口中，右击任何线程，然后单击**冻结**。  
  
2.  查看第二个列 （当前线程列）。 暂停图标现在显示那里。 这些暂停图标指示该线程已冻结。  
  
3.  显示**挂起项计数**列中选择该**列**列表。

    此时线程的挂起计数是 1。  
  
4.  右击冻结的线程，然后单击**解冻**。  
  
     当前线程列和**挂起项计数**列发生更改。 
  
## <a name="switching-the-to-another-thread"></a>切换到另一个线程 
  
#### <a name="to-switch-threads"></a>切换线程  
  
1.  在中**线程**窗口中，检查从左侧 （当前线程列） 的第二个列。 此列顶部的按钮上没有文本或图标。
  
2.  查看当前的线程列，会看到一个线程带有黄色箭头。 黄色箭头指示此线程为当前线程 （这是当前执行指针的位置）。
  
    请记下的线程 ID 号将出现当前线程图标。 会将当前线程图标移动到另一个线程，但必须将其放回时已完成。 
  
3.  右键单击另一个线程，然后单击**切换到线程**。  
  
4.  看看**调用堆栈**源代码编辑器中的窗口。 其内容已经更改。  
  
5.  看看**调试位置**工具栏。 当前线程图标也已更改。  
  
6.  转到**调试位置**工具栏。 选择从不同的线程**线程**列表。  
  
7.  看看**线程**窗口。 当前线程图标已更改。  
  
8. 在源代码编辑器中，右击线程标记。 在快捷菜单上，指向**切换到线程**单击线程名称 /ID 号。  
  
     您现在已经了解到另一个线程更改当前线程图标的三种方法： 使用**线程**窗口中，**线程**列表中**调试位置**工具栏中，并在源代码编辑器中的线程标记。  
  
     使用线程标记中，您只能切换到特定位置停止的线程。 通过使用**线程**窗口和**调试位置**工具栏中，您可以切换到任何线程。   
  
## <a name="see-also"></a>请参阅  
 [调试多线程应用程序](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [如何：在调试时切换到另一个线程](../debugger/how-to-switch-to-another-thread-while-debugging.md)
