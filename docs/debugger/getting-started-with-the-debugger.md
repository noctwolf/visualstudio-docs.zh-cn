---
title: 了解如何使用 Visual Studio 调试器进行调试
ms.description: Learn how to start the Visual Studio debugger, step through code, and inspect data.
ms.custom: mvc
ms.date: 06/15/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
helpviewer_keywords:
- debugger
ms.assetid: 62734c0d-a75a-4576-8f73-0e97c19280e1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1144e7e33709510cb03ed02cb62020f81e8e8b62
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "36303141"
---
# <a name="tutorial-learn-to-debug-using-visual-studio"></a>教程： 了解如何使用 Visual Studio 进行调试

本主题介绍了 Visual Studio 调试器中的分步演练的功能。 如果你想的调试器功能的更高级别的视图，请参阅[调试器功能简介](../debugger/debugger-feature-tour.md)。 当您*调试应用*，这通常意味着附加调试器运行应用程序。 调试器时执行此操作，提供多种方式查看你的代码执行的操作运行时。 可以逐行执行代码，并查看存储在变量中的值，可以将监视设置变量值更改时，将显示，可以检查您的代码的执行路径 et al。如果这是你在尝试调试的代码的第一个时间，可能需要阅读[零基础调试](../debugger/debugging-absolute-beginners.md)再浏览本主题。

您可以或者读取沿若要查看调试器的功能或者可以下载功能教程中使用的完整示例，按照步骤自己。 若要下载该示例并跟着介绍一起操作，请转到[照片查看器演示](https://code.msdn.microsoft.com/windowsdesktop/WPF-Photo-Viewer-Demo-be75662a)。

|         |         |
|---------|---------|
|  ![视频的摄像机图标](../install/media/video-icon.png "观看视频")  |    [观看视频](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugger-Feature-tour-of-Visual-studio-2017-sqwiwLD6D_1111787171)上调试，显示了类似的步骤。 |

尽管演示应用程序是 C#，但功能都适用于 c + +、 Visual Basic、 JavaScript 和 Visual Studio （除非另有说明） 支持其他语言。

在本教程中，你将：

> [!div class="checklist"]
> * 启动调试器并命中断点。
> * 了解单步执行代码在调试器中的命令
> * 检查数据提示和调试器窗口中的变量
> * 检查调用堆栈
> * 使用异常帮助器

## <a name="prerequisites"></a>系统必备

* 你必须安装 Visual Studio 2017 和。**NET 桌面开发**工作负荷。

    如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)页免费安装。

    如果需要安装工作负载，但已有 Visual Studio，则单击“新建项目”对话框左窗格中的“打开 Visual Studio 安装程序”链接（选择“文件” > “新建” > “项目”）。 Visual Studio 安装程序启动。 选择。**NET 桌面开发**工作负荷中，然后选择**修改**。

## <a name="start-the-debugger"></a>启动调试程序 ！

1. 若要遵循沿 Visual Studio 中执行以下步骤，下载示例[本页](https://code.msdn.microsoft.com/windowsdesktop/WPF-Photo-Viewer-Demo-be75662a)。

    > [!IMPORTANT]
    > 您需要安装.NET 桌面开发工作负荷在演示中运行应用程序，我们使用 Visual Studio。

2. 将解压缩项目。

3. 打开 Visual Studio 并选择**文件 > 打开**菜单命令，然后选择**项目/解决方案**，然后打开下载的项目的文件夹中。

     ![打开示例项目](../debugger/media/dbg-tour-open-project.png "打开项目")

3. 打开 WPF 照片查看器演示 > C# 文件夹中，选择*photoapp.sln*文件，并选择**打开**。

     在 Visual Studio 中打开该项目。 解决方案资源管理器右窗格中的显示所有项目文件。

    ![解决方案资源管理器文件](../debugger/media/dbg-tour-solution-explorer.png "解决方案资源管理器")

4. 按**F5** (**调试 > 启动调试**) 或**启动调试**按钮![开始调试](../debugger/media/dbg-tour-start-debugging.png "开始调试")调试工具栏中。

     ![照片查看器应用程序](../debugger/media/dbg-tour-wpf-app.png "照片查看器应用")

     F5 启动调试器附加到应用程序进程，但右，现在我们尚未添加任何断点或执行任何特殊操作即可检查代码应用程序。 因此应用程序只需加载并查看照片图像。

     在此教程中，我们将更详细地介绍此应用程序中使用调试器，看一看调试器功能。

5. 通过按红色 stop 停止调试器![停止调试](../debugger/media/dbg-tour-stop-debugging.png "停止调试")按钮。

## <a name="set-a-breakpoint-and-start-the-debugger"></a>设置断点并启动调试器

若要调试，需要使用调试器附加到应用程序进程启动您的应用程序。

1. 在`MainWindow`构造函数的 MainWindow.xaml.cs 中，通过单击左边的距的第一行代码中设置断点。

     ![设置断点](../debugger/media/dbg-tour-set-a-breakpoint.gif "SetABreakPoint")

    断点是可靠调试的最基本和最重要的功能。 断点指示 Visual Studio 应在哪个位置挂起你的运行代码，以使你可以查看变量的值或内存的行为，或确定代码的分支是否运行。 

6. 按**F5**或**开始调试**按钮，该应用启动时，和调试器的运行的代码行到设置了断点。

    黄色箭头表示在其暂停调试器，还在相同的点 （此语句具有尚未执行） 处挂起应用程序执行的语句。

    F5 将继续到下一个断点处运行该应用程序。 （如果尚未运行该应用程序，F5 启动调试器并在第一个断点处停止。）

    断点是代码的代码的一个有用的功能，当您知道行或你想要检查详细信息中部分。

## <a name="optional-restart-your-app-quickly"></a>（可选）快速重新启动您的应用程序

单击**重新启动**![重新启动应用程序](../debugger/media/dbg-tour-restart.png "RestartApp")调试工具栏中的按钮 (**Ctrl** + **Shift**  +  **F5**)。

当您按下**重新启动**，从而节省了时间和停止应用程序并重新启动调试器。 调试器会在执行代码被命中的第一个断点处暂停。

在调试器中设置的断点处再次停止`MainWindow`构造函数。

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>在使用单步执行命令在调试器中导航代码

大多数情况下，我们使用的键盘快捷方式，因为它是好办法获取快速在调试器 （等效命令如菜单命令显示在括号中） 中执行您的应用程序。

1. 按**F11** (**调试 > 单步执行**) 两次以转到应用的执行`InitializeComponent()`函数。

     ![使用 F11 来单步执行代码](../debugger/media/dbg-tour-f11.png "F11 单步执行")

     是 F11**单步执行**命令，并向前移动一次的应用程序执行一个语句。 F11 是检查中的大部分详细信息的执行流的好方法。 （若要通过代码更快地移动，我们介绍一些其他选项也。）默认情况下，调试器跳过非用户代码 (如果需要更多详细信息，请参阅[仅我的代码](../debugger/just-my-code.md))。

     >[!NOTE]
     > 在托管代码中，将看到一个对话框，询问您是否要在自动逐过程执行属性和运算符 （默认行为） 时得到通知。 如果你想要更改设置更高版本，禁用**逐过程执行属性和运算符**中设置**工具 > 选项**下的菜单**调试**。

2. 按**F10** (**调试 > 单步跳过**) 几次直到调试器停止的代码中的第一行上`OnApplicationStartup`事件处理程序。

     ![单步跳过代码使用 F10](../debugger/media/dbg-tour-f10-step-over.png "F10 单步跳过")

     F10 使调试器，而无需单步执行函数或方法在应用代码 （仍执行的代码）。 通过按 F10`InitializeComponent`方法调用 （而不是 F11)，我们跳过的实现代码`InitializeComponent`（我们不感兴趣现在哪些可能）。

## <a name="step-into-a-property"></a>单步执行属性

1. 使用调试器已暂停这行代码：

    ````c#
    mainWindow.Photos.Path = Environment.CurrentDirectory + "\\images";
    ````

    右键单击代码行，然后选择**单步执行特定**，然后**SDKSamples.ImageSample.PhotoCollection.Path.set**

     ![使用单步执行特定功能](../debugger/media/dbg-tour-step-into-specific.png "单步执行特定")

    如前所述，默认情况下，调试器跳过托管的属性和字段，但**单步执行特定**命令允许你重写此行为。 现在，我们要考虑会发生什么情况时`Path.set`属性 setter 运行。 **单步执行特定**获取我们到`Path.set`下面的代码。

     ![单步执行特定的结果](../debugger/media/dbg-tour-step-into-specific-2.png "单步执行特定")

     `Update`中此代码的方法看起来可能是有趣的是，现在，让我们使用的调试器来检查该代码紧密联系。

5. 将鼠标悬停`Update`方法，直到绿色**运行时单击**按钮![运行时单击](../debugger/media/dbg-tour-run-to-click.png "RunToClick")显示在左侧。

     ![使用运行到单击功能](../debugger/media/dbg-tour-run-to-click-2.png "运行时单击")

    >  [!NOTE]
    > **运行时单击**是中新增的按钮[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]。 如果看不到绿色箭头按钮，F11 在此示例中改为使用推进调试器进度。

6. 单击**运行时单击**按钮![运行时单击](../debugger/media/dbg-tour-run-to-click.png "RunToClick")。

    使用此按钮将类似于设置临时断点。 **运行时单击**便于快速入门应用程序代码 （可以单击任何打开的文件中） 的可见区域内。

    调试器将进入第`Update`方法的实现。

7. 按**F11**进入并单步`Update`方法。

     ![单步执行的 Update 方法的结果](../debugger/media/dbg-tour-update-method.png "步骤到 Update 方法")

    我们在这里找到更多代码看起来很有意思;该应用获取所有。*jpg*文件驻留在特定目录中，然后创建每个文件的照片对象。 此代码为我们提供了开始检查应用状态 （变量） 与调试器的最佳时机。 我们将在本教程的后续部分中执行的操作。

    功能，可使您可以检查变量是在调试器的最有用的功能之一，通过不同的方式来执行此操作。 通常情况下，当你尝试调试问题，您正在尝试找出变量是否存储您期望它们已在特定时间的值。

## <a name="examine-the-call-stack"></a>检查调用堆栈

在暂停时`Update`方法中，单击**调用堆栈**窗口中，这是默认情况下在右下窗格中打开。

![检查调用堆栈](../debugger/media/dbg-tour-call-stack.png "ExamineCallStack")

**调用堆栈**窗口将显示在其中调用方法和函数获取的顺序。 最上面一行显示当前函数 (`Update`教程应用程序中的方法)。 第二行显示`Update`从调用`Path.set`属性中，依次类推。

>  [!NOTE]
> **调用堆栈**窗口处于类似于调试角度来看一些 Ide，如 Eclipse。

调用堆栈是检查和了解应用的执行流的好方法。

你可以双击要查看该源代码的代码行，并还更改正在由调试器来检查当前作用域。 此操作，不再处理调试器。

此外可以使用从右键单击菜单**调用堆栈**窗口中执行其他操作。 例如，您可以将断点插入到指定的函数，请继续学习使用调试器**运行到光标处**，再检查源代码。 有关详细信息，请参阅[如何： 检查调用堆栈](../debugger/how-to-use-the-call-stack-window.md)。

## <a name="step-out"></a>跳出

假设您已完成检查`Update`方法在 Data.cs 中，并且您想要利用此函数，但仍保持在调试程序。 你可以使用**单步跳出**命令。

1. 按**Shift** + **F11** (或**调试 > 跳出**)。

     此命令恢复应用程序执行 （和使调试器），直到当前函数返回。

     应返回`Update`Data.cs 中的方法调用。

2. 按**Shift** + **F11**同样，而在调试器进入调用堆栈中向上返回到`OnApplicationStartup`事件处理程序。

## <a name="run-to-cursor"></a>运行到光标处

1. 选择**停止调试**红色按钮![停止调试](../debugger/media/dbg-tour-stop-debugging.png "停止调试")或者**Shift** + **F5**.

2. 在中`Update`中的方法*Data.cs*，右键单击`Add`方法调用，并选择**运行到光标处**。 此命令启动调试，并在当前代码行上设置临时断点。

     ![使用运行到游标功能](../debugger/media/dbg-tour-run-to-cursor.png "运行到光标处")

    您应该在断点处暂停`MainWindow`（因为它是第一个断点设置）。

3. 按**F5**转到`Add`其中所选的方法**运行到光标处**。

    当你编辑代码并想要快速设置临时断点，然后启动调试器时，此命令很有用。

## <a name="change-the-execution-flow"></a>更改执行流

1. 使用调试器上暂停`Add`方法调用时，使用鼠标在左侧的黄色箭头 （执行指针） 获取并移动到一个行的黄色箭头`foreach`循环。

     ![将执行指针移至](../debugger/media/dbg-tour-move-the-execution-pointer.gif "将执行指针移动")

    通过更改执行流，可以执行某些操作，如测试不同的代码执行路径或重新运行代码，而无需重新启动调试器。

2. 现在，请按**F5**。

    您可以看到添加到应用程序窗口的图像。 因为重新运行中的代码`foreach`已两次添加循环中，某些图像 ！

    > [!WARNING]
    > 通常需要谨慎使用此功能，并查看工具提示中的警告。 您也可能会看到其他警告。 移动指针不能还原到以前的应用程序状态的应用程序。

## <a name="inspect-variables-with-data-tips"></a>检查与数据提示中的变量

1. 打开*Data.cs*在照片查看器演示应用中，右键单击`private void Update`函数声明，然后选择**运行到光标处**（停止此应用程序首先如果它已在运行）。

    这将使用附加调试器暂停应用程序。 这样，我们要检查其状态。

2. 将鼠标悬停`Add`方法调用，然后单击**运行时单击**按钮![运行时单击](../debugger/media/dbg-tour-run-to-click.png "RunToClick")。

3. 现在，将鼠标悬停文件对象 (`f`)，并查看其默认属性值的文件的名称*市场 031.jpg*。

     ![查看数据提示](../debugger/media/dbg-tour-data-tips.gif "查看数据提示")

4. 展开该对象以查看所有其属性，如`FullPath`属性。

    通常情况下，在调试时，你想要快速检查对象的属性值和数据提示是执行此操作的好办法。

    > [!TIP]
    > 在最支持的语言，可编辑调试器会话的中间代码，如果你找到你想要更改的内容。 有关详细信息，请参阅[编辑并继续](../debugger/edit-and-continue.md)。 若要在此应用中使用该功能，但是，我们将首先需要更新的.NET framework 的应用程序的版本。

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>检查与自动和局部变量窗口中的变量

1. 看看**自动**底部的代码编辑器窗口。

     ![检查自动窗口中的变量](../debugger/media/dbg-tour-autos-window.png "自动窗口")

    在中**自动**窗口中，请参阅变量和其当前值。 **自动**窗口显示当前行或在前面的行上使用的所有变量 （在 c + + 中，窗口将都显示变量中前三行代码。 查看文档，了解特定于语言的行为）。

    > [!NOTE]
    > 在 JavaScript 中，**局部变量**但不是支持窗口**自动**窗口。

2. 接下来，看看**局部变量**窗口。

    **局部变量**窗口显示当前作用域中的变量。

    ![检查局部变量窗口中的变量](../debugger/media/dbg-tour-locals-window.png "局部变量窗口")

    目前，`this`对象和文件对象 (`f`) 在当前范围内。 有关详细信息，请参阅[检查变量中的自动和局部变量 Windows](../debugger/autos-and-locals-windows.md)。

## <a name="set-a-watch"></a>设置监视

1. 在主代码编辑器窗口中，右键单击文件对象 (`f`)，然后选择**添加监视**。

    可以使用**监视**窗口上指定一个变量 （或表达式），你想要密切关注。

    现在，可以监视上设置`File`对象，您可以看到当移动通过调试程序时更改其值。 与其他变量窗口中，不同**监视**窗口始终显示的变量，观看 （它们灰显时超出范围）。

2. 上`Add`方法中，单击绿色![运行时单击](../debugger/media/dbg-tour-run-to-click.png "RunToClick")按钮再次 （或按 F11 几次） 若要向前移动`foreach`循环。

    ![对变量设置监视](../debugger/media/dbg-tour-watch-window.png "监视窗口")

    您可能还会看到第一张图片添加到主窗口中运行的示例应用程序，但这发生在不同的应用程序线程，因此映像可能不会显示尚未。

    有关详细信息，请参阅[设置使用监视和快速监视 Windows 监视](../debugger/watch-and-quickwatch-windows.md)

## <a name="examine-an-exception"></a>检查异常

1. 在正在运行的应用程序窗口中，删除中的文本**路径**输入的框，然后选择**更改**按钮。

     ![导致引发异常](../debugger/media/dbg-tour-cause-an-exception.png "会导致异常")

     应用程序将引发异常，，则调试器会引发异常的代码行。

     ![异常帮助器](../debugger/media/dbg-tour-exception-helper.png "异常帮助器")

     在这里，**异常帮助程序**演示了`System.ArgumentException`和错误消息，指出该路径不是合法的窗体。 因此，我们知道该错误出现在方法或函数的参数。

     在此示例中，`DirectoryInfo`调用中存储的空字符串的帮助错误`value`变量。 (将鼠标悬停`value`若要查看的空字符串。)

     异常帮助器是一项强大功能可帮助你调试错误。 此外可以执行诸如查看错误详细信息，并从异常帮助程序添加监视。 或者，如果需要可以更改引发特定异常的条件。

    >  [!NOTE]
    > 异常帮助器将替换中的助手异常[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]。

2. 展开**异常设置**节点以查看更多选项如何处理此异常类型，但你无需更改此教程中的任何内容 ！

3. 按 F5 继续。

若要了解有关调试器的功能的详细信息，请参阅[调试器提示和技巧](../debugger/debugger-tips-and-tricks.md)。

## <a name="next-steps"></a>后续步骤

在本教程中，已学习了如何启动调试器，单步执行代码，并检查变量。 您可能想要深入了解调试器功能，此外还提供详细信息链接。

> [!div class="nextstepaction"]
> [调试器功能简介](../debugger/debugger-feature-tour.md)
