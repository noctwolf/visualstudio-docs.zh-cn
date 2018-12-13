---
title: 了解如何调试多线程应用程序
description: 使用 Visual Studio 中的并行堆栈和并行监视窗口进行调试
ms.custom: H1HackMay2017
ms.date: 11/16/2018
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
ms.assetid: 62df746b-b0f6-4df4-83cf-b1d9d2e72833
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2a6ded522a917dd7207da7731850303535e19fdb
ms.sourcegitcommit: 54c65f81a138fc1e8ff1826f7bd9dcec710618cc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2018
ms.locfileid: "51948980"
---
# <a name="get-started-debugging-multithreaded-applications"></a>开始调试多线程应用程序
Visual Studio 提供多种工具和用户界面元素，以帮助您调试多线程应用程序。 本教程演示如何使用线程标记**并行堆栈**窗口中，**并行监视**窗口中，条件断点，并筛选器断点。 完成本教程将使您熟悉用于调试多线程应用程序的 Visual Studio 功能。

| | |
|---------|---------|
| ![视频的摄像机图标](../install/media/video-icon.png "观看视频") | [观看视频](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugging-Multi-threaded-Apps-in-Visual-Studio-2017-MoZPKMD6D_111787171)上显示了类似的步骤的多线程调试。 |

这两个主题提供有关使用其他多线程调试工具的其他信息：

- 若要使用**调试位置**工具栏和**线程**窗口中，请参阅[演练： 调试多线程应用程序](../debugger/how-to-use-the-threads-window.md)。

- 有关使用的示例<xref:System.Threading.Tasks.Task>（托管代码） 和并发运行时 （c + +），请参阅[演练： 调试并行应用程序](../debugger/walkthrough-debugging-a-parallel-application.md)。 有关适用于最多线程应用程序类型的常规调试提示，读取该主题和此。
  
首先需要一个多线程应用程序项目。 以下是一个示例。  
  
## <a name="create-a-multithreaded-app-project"></a>创建一个多线程应用程序项目  
  
1.  在“文件”菜单上，选择“新建” > “项目”。  
  
     此时将出现 “新建项目” 对话框。  
  
2.  选择一种语言：**可视化C#** ， **Visual c + +**，或**Visual Basic**。  
  
3.  下**Windows 桌面**，选择**控制台应用**。  
  
4.  在中**名称**字段中，输入 MyThreadWalkthroughApp。  
  
5.  选择“确定”。  
  
     新的控制台项目随即显示。 创建项目后，会出现一个源代码文件。 根据您选择的语言，源文件可能会调用*Program.cs*， *MyThreadWalkthroughApp.cpp*，或*Module1.vb*。  
  
6.  删除出现在源代码文件中的代码并将它替换下面列出的相应示例代码。

    ```csharp
    using System;
    using System.Threading;

    public class ServerClass
    {

        static int count = 0;
        // The method that will be called when the thread is started.
        public void InstanceMethod()
        {
            Console.WriteLine(
                "ServerClass.InstanceMethod is running on another thread.");

            int data = count++;
            // Pause for a moment to provide a delay to make
            // threads more apparent.
            Thread.Sleep(3000);
            Console.WriteLine(
                "The instance method called by the worker thread has ended.");
        }
    }

    public class Simple
    {
        public static void Main()
        {
            for (int i = 0; i < 10; i++)
            {
                CreateThreads();
            }
        }
        public static void CreateThreads()
        {
            ServerClass serverObject = new ServerClass();

            Thread InstanceCaller = new Thread(new ThreadStart(serverObject.InstanceMethod));
            // Start the thread.
            InstanceCaller.Start();

            Console.WriteLine("The Main() thread calls this after "
                + "starting the new InstanceCaller thread.");

        }
    }
    ```

    ```C++
    #include "stdafx.h"
    #include <thread>
    #include <iostream>
    #include <vector>

    using namespace;

    int count = 0;

    void doSomeWork() {

        cout << "The doSomeWork function is running on another thread." << endl;
        int data = count++;
        // Pause for a moment to provide a delay to make
        // threads more apparent.
        this_thread::sleep_for(chrono::seconds(3));
        cout << "The function called by the worker thread has ended." << endl;
    }

    int main() {
        vector<thread> threads;

        for (int i = 0; i < 10; ++i) {

            threads.push_back(thread(doSomeWork));
            cout << "The Main() thread calls this after starting the new thread" << endl;
        }

        for (auto& thread : threads) {
            thread.join();
        }

        return 0;
    }
    ```

    ```VB
    Imports System.Threading

    Public Class ServerClass
        ' The method that will be called when the thread is started.
        Public count = 0
        Public Sub InstanceMethod()
            Console.WriteLine(
                    "ServerClass.InstanceMethod is running on another thread.")

            Dim data = count + 1
            ' Pause for a moment to provide a delay to make
            ' threads more apparent.
            Thread.Sleep(3000)
            Console.WriteLine(
                    "The instance method called by the worker thread has ended.")
        End Sub

    End Class

    Public Class Simple

        Public Shared Sub Main()

            Dim ts As New ThreadStarter
            For index = 1 To 10
                ts.CreateThreads()
            Next

        End Sub

    End Class
    Public Class ThreadStarter
        Public Sub CreateThreads()
            Dim serverObject As New ServerClass()

            ' Create the thread object, passing in the
            ' serverObject.InstanceMethod method using a
            ' ThreadStart delegate.
            Dim InstanceCaller As New Thread(AddressOf serverObject.InstanceMethod)

            ' Start the thread.
            InstanceCaller.Start()

            Console.WriteLine("The Main() thread calls this after " _
                        + "starting the new InstanceCaller thread.")

        End Sub
    End Class
    ```
  
7.  上**文件**菜单中，选择**全部保存**。  
  
## <a name="debug-the-multithreaded-app"></a>调试多线程应用程序  
  
1. 在源代码编辑器中，查找以下代码段之一： 
  
    ```csharp  
    Thread.Sleep(3000);  
    Console.WriteLine();  
    ```  
  
    ```C++  
    this_thread::sleep_for(chrono::seconds(3));
    cout << "The function called by the worker thread has ended." << endl; 
    ```  

    ```VB
    Thread.Sleep(3000)
    Console.WriteLine()
    ```

1. 左键单击中的左滚动条槽`Thread.Sleep`或`this_thread::sleep_for`语句将新断点。  
  
    滚动条槽中的红色圆圈指示在此位置设置断点。 
  
2. 上**调试**菜单中，选择**开始调试**(**F5**)。  
  
    Visual Studio 生成该解决方案、 应用程序开始运行附带，调试器，然后应用程序停止在断点处。  
  
3. 在源代码编辑器中，找到包含该断点的行。
  
### <a name="ShowThreadsInSource"></a>发现线程标记  

1.  在调试工具栏中，选择**源中显示线程**按钮![在源中显示线程](../debugger/media/dbg-multithreaded-show-threads.png "ThreadMarker")。

2. 按**F11**一次以前进的调试器一个代码行。
  
3.  查看窗口左侧的滚动条槽。 在此行中，你会看到*线程标记*图标![线程标记](../debugger/media/dbg-thread-marker.png "ThreadMarker") ，类似于两个扭曲的线程。 线程标记指示线程在此位置停止。

    线程标记可能会部分隐藏的断点。 
  
4.  将指针悬停在线程标记上。 数据提示显示告诉你为每个已停止线程的名称和线程 ID 号。 在这种情况下，名称可能是`<noname>`。 
  
5.  选择要查看的快捷菜单上的可用选项的线程标记。
    
### <a name="ParallelStacks"></a>查看线程位置

在中**并行堆栈**窗口中，您可以切换线程视图之间和 （适用于基于任务的编程） 任务视图，您可以查看每个线程的调用堆栈信息。 在此应用中，我们可以使用线程视图。

1. 打开**并行堆栈**通过选择窗口**调试** > **Windows** > **并行堆栈**。 应看到类似于以下内容。 根据每个线程，您的硬件和您的编程语言的当前位置将不同的准确信息。

    ![并行堆栈窗口](../debugger/media/dbg-multithreaded-parallel-stacks.png "ParallelStacksWindow")

    在此示例中，从左到右我们看到此信息对于托管代码：
    
    - 主线程 （左侧） 上已停止`Thread.Start`、 停止点将由线程标记图标![线程标记](../debugger/media/dbg-thread-marker.png "ThreadMarker")。
    - 输入的两个线程`ServerClass.InstanceMethod`，其中之一是当前线程 （黄色箭头），而另一个线程已停止在`Thread.Sleep`。
    - （右侧） 一个新线程还从开始，但上停止`ThreadHelper.ThreadStart`。

2.  右键单击中的条目**并行堆栈**窗口来查看快捷菜单上的可用选项。

    您可以执行各种操作从这些右键单击菜单中，但对于本教程中我们将显示多个中的这些详细信息**并行监视**窗口 （下一节）。

    > [!NOTE]
    > 若要查看列表视图，每个线程上的信息，请使用**线程**窗口相反。 请参阅[演练： 调试多线程应用程序](../debugger/how-to-use-the-threads-window.md)。

### <a name="set-a-watch-on-a-variable"></a>对变量设置监视

1. 打开**并行监视**通过选择窗口**调试** > **Windows** > **并行监视** > **并行监视 1**。

2. 选择在其中查看该单元格`<Add Watch>`文本 （或中的第 4 列的空标头单元格），然后输入`data`。

    在窗口中显示每个线程的数据变量的值。

3. 选择在其中查看该单元格`<Add Watch>`文本 （或第五个列中的空标头单元格），然后输入`count`。

    值`count`窗口中显示为每个线程的变量。 如果看不到这么多的信息，请尝试按**F11**几次以继续在调试器中线程的执行。

    ![并行监视窗口](../debugger/media/dbg-multithreaded-parallel-watch.png "ParallelWatchWindow")

4. 右键单击其中一个窗口以查看可用选项中的行。

### <a name="flag-and-unflag-threads"></a>标记线程和取消标记线程  
您可以标记跟踪重要线程并忽略其他线程的线程。  
  
1. 在中**并行监视**窗口中，按住**Shift**键并选择多个行。

2. 右键单击并选择**标志**。

    所选的所有线程都将都标记。 现在，您可以筛选为仅显示已标记的线程。
  
3.  在中**并行监视**窗口中，选择**仅显示标记的线程**按钮![显示已标记线程](../debugger/media/dbg-threads-show-flagged.png "ThreadMarker")。  
  
    标记的线程显示在列表中。

    > [!TIP]
    > 已标记某些线程后，可以右键单击代码编辑器中的代码行，然后选择**运行到光标处的已标记线程**。 请确保选择所有标记的线程的代码将访问。 Visual Studio 将暂停线程代码中，在所选行上的更轻松地控制的执行顺序[冻结和解冻线程](#bkmk_freeze)。

4.  选择**仅显示标记的线程**按钮将再次切换回**显示所有线程**模式。
    
5. 若要取消标记线程，右键单击一个或多个标记的线程中**并行监视**窗口，然后选择**取消标记**。

### <a name="bkmk_freeze"></a> 冻结和解冻线程执行 

> [!TIP]
> 您可以冻结和解冻 （暂停和恢复） 线程来控制线程在其中执行工作的顺序。 这可以帮助你解决并发问题，例如死锁和争用条件。
   
1.  在中**并行监视**窗口中，与所有选定的行，右键单击并选择**冻结**。

    在第二列中的每一行将显示一个暂停图标。 暂停图标指示该线程已冻结。

2.  通过选择一个行仅取消选择所有其他行。

3.  右键单击某一行，然后选择**解冻**。

    暂停图标指示线程已不再被冻结此行上会消失。

4.  切换到代码编辑器，并按**F11**。 仅在未冻结的线程运行。

    应用还实例化某些新线程。 取消标记和未冻结任何新线程。

### <a name="bkmk_follow_a_thread"></a> 请按照具有条件断点的单一线程

它可能有助于按照在调试器中单线程的执行。 若要执行此操作的一种方法是通过冻结您不感兴趣的线程。 在某些情况下可能需要操作单个线程，并且不冻结其他线程，例如若要重新生成某一特定错误。 若要执行一个线程不冻结其他线程的情况下，必须避免中断到除你感兴趣的线程上的代码。 您可以执行此操作通过设置[条件断点](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)。

可以在不同的条件，例如，线程名称或线程 ID 上设置断点 可能会将条件设置您知道是唯一的每个线程的数据是很有帮助。 这是常见的调试方案中，你会更感兴趣比任何特定的线程中的一些特定的数据值。

1. 右键单击以前创建的断点并选择**条件**。

2. 在中**断点设置**窗口中，输入`data == 5`为条件表达式。

    ![条件断点](../debugger/media/dbg-multithreaded-conditional-breakpoint.png "ConditionalBreakpoint")

    > [!TIP]
    > 如果要更感兴趣的特定线程，然后使用线程名称或线程 ID，条件。 若要执行此操作**断点设置**窗口中，选择**筛选器**而不是**条件表达式**，并按照筛选器提示。 您可能需要命名在应用代码中，您的线程的线程 Id 更改时重新启动调试器。

3. 关闭**断点设置**窗口。

4. 选择在重新启动![重新启动应用程序](../debugger/media/dbg-tour-restart.png "RestartApp")按钮以重新启动调试会话。

    将中断到其中的数据变量的值为 5 的线程上的代码。 在中**并行监视**窗口中查看，该值指示当前的调试器上下文的黄色箭头。

5. 现在，可以单步执行代码 (**F10**) 和单步执行代码 (**F11**) 并按照单个线程执行。

    只要断点条件是唯一的线程，且调试器不会命中 （可能需要禁用它们） 的其他线程上的任何其他断点，可以单步执行代码并单步执行代码而无需切换到其他线程。

    > [!NOTE]
    > 当您推进调试器进度时，将运行所有线程。 但是，调试器不会中断到其他线程上的代码中，除非其中一个其他线程遇到断点。 
  
## <a name="see-also"></a>请参阅  
[调试多线程应用程序](../debugger/debug-multithreaded-applications-in-visual-studio.md)  
[如何：在调试时切换到另一个线程](../debugger/how-to-switch-to-another-thread-while-debugging.md)  
[如何： 使用并行堆栈窗口](../debugger/using-the-parallel-stacks-window.md)  
[如何：使用“并行监视”窗口](../debugger/how-to-use-the-parallel-watch-window.md)  
