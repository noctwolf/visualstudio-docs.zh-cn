---
title: 了解如何使用 Visual Studio 调试器进行调试
ms.description: Learn how to start the Visual Studio debugger, step through code, and inspect data.
ms.custom: mvc
ms.date: 08/01/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
dev_langs:
- CSharp
- C++
helpviewer_keywords:
- debugger
ms.assetid: 62734c0d-a75a-4576-8f73-0e97c19280e1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 235e9386070d316cd9a4f9751ac1d8f1e8fd92b4
ms.sourcegitcommit: db94ca7a621879f98d4c6aeefd5e27da1091a742
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2018
ms.locfileid: "42623851"
---
# <a name="tutorial-learn-to-debug-using-visual-studio"></a>教程： 了解如何使用 Visual Studio 进行调试

本文介绍了 Visual Studio 调试器中的分步演练的功能。 如果你想的调试器功能的更高级别的视图，请参阅[调试器功能简介](../debugger/debugger-feature-tour.md)。 当您*调试应用*，这通常意味着附加调试器运行应用程序。 调试器时执行此操作，提供多种方式查看你的代码执行的操作运行时。 您可以单步执行代码，并查看存储在变量中的值，您可以设置监视变量以查看值发生更改时，您可以检查您的代码的执行路径，请参阅代码的分支是否正在运行，等等。 如果这是你在尝试调试的代码的第一个时间，可能需要阅读[零基础调试](../debugger/debugging-absolute-beginners.md)之前开始阅读本文。

|         |         |
|---------|---------|
|  ![视频的摄像机图标](../install/media/video-icon.png "观看视频")  |    [观看视频](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Debugger-Feature-tour-of-Visual-studio-2017-sqwiwLD6D_1111787171)上调试，显示了类似的步骤。 |

尽管演示应用程序是 C# 和 c + +，但功能都适用于 Visual Basic、 JavaScript 和 Visual Studio （除非另有说明） 支持其他语言。 屏幕截图与 C# 中。 若要切换 C# 和 c + + 示例代码，请使用页面的右上角的语言筛选器。

在本教程中，你将：

> [!div class="checklist"]
> * 启动调试器并命中断点。
> * 了解单步执行代码在调试器中的命令
> * 检查数据提示和调试器窗口中的变量
> * 检查调用堆栈

## <a name="prerequisites"></a>系统必备

* 你必须安装 Visual Studio 2017 并 **.NET 桌面开发**或**使用 c + + 的桌面开发**工作负荷。

    如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)页免费安装。

    如果需要安装工作负载，但已有 Visual Studio，则单击“新建项目”对话框左窗格中的“打开 Visual Studio 安装程序”链接（选择“文件” > “新建” > “项目”）。 Visual Studio 安装程序启动。 选择。**NET 桌面开发**或**使用 c + + 的桌面开发**工作负荷中，然后选择**修改**。

## <a name="create-a-project"></a>创建项目

1. 在 Visual Studio 中，依次选择“文件”>“新建项目”。

2. 下**Visual C#** 或**Visual c + +**，选择**Windows 桌面**，然后在中间窗格中选择**控制台应用**(**Windows 控制台应用程序**c + + 中)。

    如果没有看到**控制台应用程序**项目模板，请单击**打开 Visual Studio 安装程序**的左窗格中的链接**新项目**对话框。 Visual Studio 安装程序启动。 选择 *.NET 桌面开发** 或**使用 c + + 的桌面开发**工作负荷中，然后选择**修改**。

3. 键入一个名称，如**获取启动调试**然后单击**确定**。

    Visual Studio 随即创建项目。

4. 在中*Program.cs* (C#) 或*get 启动 debugging.cpp* （c + +），将以下代码

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;

    namespace get_started_debugging
    {
        class Program
        {
            static void Main(string[] args)
            {
            }
        }
    }
    ```

    ```c++
    int main()
    {
        return 0;
    }
    ```

    替换为此代码：

    ```csharp
    using System;
    using System.Collections.Generic;

    public class Shape
    {
        // A few example members
        public int X { get; private set; }
        public int Y { get; private set; }
        public int Height { get; set; }
        public int Width { get; set; }
   
        // Virtual method
        public virtual void Draw()
        {
            Console.WriteLine("Performing base class drawing tasks");
        }
    }

    class Circle : Shape
    {
        public override void Draw()
        {
            // Code to draw a circle...
            Console.WriteLine("Drawing a circle");
            base.Draw();
        }
    }

    class Rectangle : Shape
    {
        public override void Draw()
        {
            // Code to draw a rectangle...
            Console.WriteLine("Drawing a rectangle");
            base.Draw();
        }
    }

    class Triangle : Shape
    {
        public override void Draw()
        {
            // Code to draw a triangle...
            Console.WriteLine("Drawing a trangle");
            base.Draw();
        }
    }

    class Program
    {
        static void Main(string[] args)
        {

            var shapes = new List<Shape>
            {
                new Rectangle(),
                new Triangle(),
                new Circle()
            };

            foreach (var shape in shapes)
            {
                shape.Draw();
            }

            // Keep the console open in debug mode.
            Console.WriteLine("Press any key to exit.");
            Console.ReadKey();
        }

    }

    /* Output:
        Drawing a rectangle
        Performing base class drawing tasks
        Drawing a triangle
        Performing base class drawing tasks
        Drawing a circle
        Performing base class drawing tasks
    */
    ```

    ```c++
    #include "pch.h"

    #include <string>
    #include <vector>
    #include <iostream>

    class Shape
    {
        int privateX = 0;
        int privateY = 0;
        int privateHeight = 0;
        int privateWidth = 0;

        int getX() const { return privateX; }
        void setX(int value) { privateX = value; }

        int getY() const { return privateY; }
        void setY(int value) { privateY = value; }

        int getHeight() const { return privateHeight; }
        void setHeight(int value) { privateHeight = value; }

        int getWidth() const { return privateWidth; }
        void setWidth(int value) { privateWidth = value; }

        public:
        // Virtual method
        virtual void Draw()
        {
            std::wcout << L"Performing base class drawing tasks" << std::endl;
        }
    };

    class Circle : public Shape
    {
        public:
        void Draw() override
        {
        // Code to draw a circle...
        std::wcout << L"Drawing a circle" << std::endl;
        Shape::Draw();
        }
    };

    class Rectangle : public Shape
    {
        public:
        void Draw() override
        {
        // Code to draw a rectangle...
        std::wcout << L"Drawing a rectangle" << std::endl;
        Shape::Draw();
        }
    };

    class Triangle : public Shape
    {
        public:
        void Draw() override
        {
        // Code to draw a triangle...
        std::wcout << L"Drawing a trangle" << std::endl;
        Shape::Draw();
        }
    };

    int main(std::vector<std::wstring> &args)
    {
        auto shapes = std::vector<Shape*>
        {
            new Rectangle(),
            new Triangle(),
            new Circle()
        };

        for (auto shape : shapes)
        {
            shape->Draw();
        }
    }

    /* Output:
    Drawing a rectangle
    Performing base class drawing tasks
    Drawing a triangle
    Performing base class drawing tasks
    Drawing a circle
    Performing base class drawing tasks
    */
    ```

## <a name="start-the-debugger"></a>启动调试程序 ！

1. 按**F5** (**调试 > 启动调试**) 或**启动调试**按钮![开始调试](../debugger/media/dbg-tour-start-debugging.png "开始调试")调试工具栏中。

     **F5**启动应用程序与调试程序附加到应用程序处理，但现在，我们还没有做任何特殊操作即可检查代码。 因此该应用程序只需加载并查看的控制台输出。

    ```
    Drawing a rectangle
    Performing base class drawing tasks
    Drawing a triangle
    Performing base class drawing tasks
    Drawing a circle
    Performing base class drawing tasks
    ```

     在本教程中，我们将更详细地介绍此应用程序中使用调试器，看一看调试器功能。

2. 通过按红色 stop 停止调试器![停止调试](../debugger/media/dbg-tour-stop-debugging.png "停止调试")按钮。

## <a name="set-a-breakpoint-and-start-the-debugger"></a>设置断点并启动调试器

1. 在中`foreach`循环`Main`函数 (`for` c + + 中的循环`main`函数)，通过单击左边的距的第一行代码中设置断点。

    ![设置断点](../debugger/media/get-started-set-breakpoint.png "SetABreakPoint")

    将断点设置会显示一个红色圆圈。

    断点是可靠调试的最基本和最重要的功能。 断点指示 Visual Studio 应在哪个位置挂起你的运行代码，以使你可以查看变量的值或内存的行为，或确定代码的分支是否运行。 

6. 按**F5**或**开始调试**按钮，该应用启动时，和调试器的运行的代码行到设置了断点。

    ![命中断点](../debugger/media/get-started-hit-breakpoint.png "HitABreakPoint")

    黄色箭头表示在其暂停调试器，还在相同的点 （此语句具有尚未执行） 处挂起应用程序执行的语句。

     如果应用尚未运行， **F5**启动调试器并在第一个断点处停止。 否则为**F5**运行的应用程序运行到下一个断点。

    断点是代码的代码的一个有用的功能，当您知道行或你想要检查详细信息中部分。

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>在使用单步执行命令在调试器中导航代码

大多数情况下，我们使用的键盘快捷方式，因为它是好办法获取快速在调试器 （等效命令如菜单命令显示在括号中） 中执行您的应用程序。

1. 按**F11** (或选择**调试 > 单步执行**) （多次在 C# 中) 的一次上暂停直到`shape.Draw`方法调用中`Main`方法 (`shape->Draw` c + + 中)。

1. 按**F11**一次以转到代码`Rectangle`类。

     ![使用 F11 来单步执行代码](../debugger/media/get-started-f11.png "F11 单步执行")

     是 F11**单步执行**命令，并向前移动一次的应用程序执行一个语句。 F11 是检查中的大部分详细信息的执行流的好方法。 （若要通过代码更快地移动，我们介绍一些其他选项也。）默认情况下，调试器跳过非用户代码 (如果需要更多详细信息，请参阅[仅我的代码](../debugger/just-my-code.md))。

2. 按**F10** (或选择**调试 > 单步跳过**) 几次，直到上停止调试器`base.Draw`方法调用 (`Shape::Draw` c + + 中)，然后按**F10**再来一次。

     ![单步跳过代码使用 F10](../debugger/media/get-started-step-over.png "F10 单步跳过")

     请注意这次不，调试器不会单步执行`Draw`基类的方法 (`Shape`)。 **F10**使调试器，而无需单步执行函数或方法在应用代码 （仍执行的代码）。 通过按 F10 `base.Draw` (或`Shape::Draw`) 方法调用 (而不是**F11**)，我们跳过的实现代码`base.Draw`（我们不感兴趣现在哪些可能）。

## <a name="navigate-code-using-run-to-click"></a>导航代码中使用运行时单击

5. 在代码编辑器中，向下滚动并悬停`Console.WriteLine`方法 (`std::cout` c + + 中) 中`Triangle`直到绿色类**运行时单击**按钮![运行时单击](../debugger/media/dbg-tour-run-to-click.png "RunToClick")显示在左侧。

     ![使用运行到单击功能](../debugger/media/get-started-run-to-click.png "运行时单击")

    >  [!NOTE]
    > **运行时单击**是中新增的按钮[!include[vs_dev15](../misc/includes/vs_dev15_md.md)]。 如果看不到绿色箭头按钮，使用**F11**在此示例中改为使调试器前进到正确的位置。

6. 单击**运行时单击**按钮![运行时单击](../debugger/media/dbg-tour-run-to-click.png "RunToClick")。

    使用此按钮将类似于设置临时断点。 **运行时单击**便于快速入门应用程序代码 （可以单击任何打开的文件中） 的可见区域内。

    调试器将进入第`Console.WriteLine`方法实现`Triangle`类 (`std::cout` c + + 中)。

    在暂停时，你注意到有拼写错误 ！ "绘制 trangle"的输出是拼写错误。 我们可以在调试器中运行应用程序时修复它就在这里。

## <a name="edit-code-and-continue-debugging"></a>编辑代码并继续调试

1. 单击"绘制 trangle"并键入更正，将"trangle"更改为"triangle"。

1. 按**F11**一次，你会看到调试器再次前移。

    > [!NOTE]
    > 具体取决于在调试器中编辑的代码类型，可能会看到一条警告消息。 在某些情况下，代码将需要重新编译，然后才能继续。

## <a name="step-out"></a>跳出

假设您已完成检查`Draw`中的方法`Triangle`类，并且你想要利用此函数，但仍保持在调试程序。 你可以使用**单步跳出**命令。

1. 按**Shift** + **F11** (或**调试 > 跳出**)。

     此命令恢复应用程序执行 （和使调试器），直到当前函数返回。

     应为回到`foreach`循环`Main`方法 (`for` c + + 中的循环)。

## <a name="restart-your-app-quickly"></a>快速重新启动您的应用程序

单击**重新启动**![重新启动应用程序](../debugger/media/dbg-tour-restart.png "RestartApp")调试工具栏中的按钮 (**Ctrl** + **Shift**  +  **F5**)。

当您按下**重新启动**，从而节省了时间和停止应用程序并重新启动调试器。 调试器会在执行代码被命中的第一个断点处暂停。

在调试器中设置的断点处停止再次`foreach`循环 (`for` c + + 中的循环)。

## <a name="inspect-variables-with-data-tips"></a>检查与数据提示中的变量

功能，可使您可以检查变量是在调试器的最有用的功能之一，通过不同的方式来执行此操作。 通常情况下，当你尝试调试问题，您正在尝试找出变量是否存储您期望它们已在特定时间的值。

1. 在暂停时`foreach`循环 (`for` c + + 中的循环)，按**F11**后。

1. 将鼠标悬停`shapes`对象，并查看其默认属性值`Count`属性。

1. 展开`shapes`对象以查看所有属性，如数组的第一个索引`[0]`，其中包含的值为`Rectangle`(C#) 或内存地址 （c + +）。

     ![查看数据提示](../debugger/media/get-started-data-tip.png "查看数据提示")

    通常情况下，在调试时，你想要快速检查对象的属性值和数据提示是执行此操作的好办法。

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>检查与自动和局部变量窗口中的变量

1. 看看**自动**底部的代码编辑器窗口。

     ![检查自动窗口中的变量](../debugger/media/get-started-autos-window.png "自动窗口")

    在中**自动**窗口中，请参阅变量和其当前值。 **自动**窗口显示当前行或在前面的行上使用的所有变量 （在 c + + 中，窗口将都显示变量中前三行代码。 查看文档，了解特定于语言的行为）。

    > [!NOTE]
    > 在 JavaScript 中，**局部变量**但不是支持窗口**自动**窗口。

2. 接下来，看看**局部变量**窗口中，在下一步的选项卡**自动**窗口。

    **局部变量**窗口显示在当前的变量[作用域](https://www.wikipedia.org/wiki/Scope_(computer_science))。

## <a name="set-a-watch"></a>设置监视

1. 在主代码编辑器窗口中，右键单击`shapes`对象，并选择**添加监视**。

    **监视**窗口将打开代码编辑器的底部。 可以使用**监视**窗口上指定一个变量 （或表达式），你想要密切关注。

    现在，可以监视上设置`shapes`对象，您可以看到当移动通过调试程序时更改其值。 与其他变量窗口中，不同**监视**窗口始终显示的变量，观看 （它们灰显时超出范围）。

## <a name="examine-the-call-stack"></a>检查调用堆栈

1. 在暂停时`foreach`循环 (`for` c + + 中的循环)，单击**调用堆栈**窗口中，这是默认情况下在右下窗格中打开。

1. 单击**F11**几次，直到您看到调试器中暂停`Circle.Draw`代码编辑器中的方法。 看看**调用堆栈**窗口。

    ![检查调用堆栈](../debugger/media/get-started-call-stack.png "ExamineCallStack")

    **调用堆栈**窗口将显示在其中调用方法和函数获取的顺序。 最上面一行显示当前函数 (`Circle.Draw`或`Circle::Draw`此应用程序中的方法)。 第二行显示`Circle.Draw`从调用`Main`方法 (`main` c + + 中)，依次类推。

    >  [!NOTE]
    > **调用堆栈**窗口处于类似于调试角度来看一些 Ide，如 Eclipse。

    调用堆栈是检查和了解应用的执行流的好方法。

    你可以双击要查看该源代码的代码行，并还更改正在由调试器来检查当前作用域。 此操作，不再处理调试器。

    此外可以使用从右键单击菜单**调用堆栈**窗口中执行其他操作。 例如，您可以将断点插入到指定的函数，请继续学习使用调试器**运行到光标处**，再检查源代码。 有关详细信息，请参阅[如何： 检查调用堆栈](../debugger/how-to-use-the-call-stack-window.md)。

## <a name="change-the-execution-flow"></a>更改执行流

1. 使用调试器中暂停`Circle.Draw`方法调用中，按**F11**几次，直到上暂停调试器`base.Draw`方法调用 (`Shape::Draw` c + + 中)。

1. 使用鼠标抓取在左侧的黄色箭头 （执行指针） 并将移动到一个行的黄色箭头`Console.WriteLine`(`std::cout`中 c + +) 方法调用。

1. 按**F11**多一次。

    重新运行调试器`Console.WriteLine`方法 (`std::cout` c + + 中)。

    通过更改执行流，可以执行某些操作，如测试不同的代码执行路径或重新运行代码，而无需重新启动调试器。

    > [!WARNING]
    > 通常需要谨慎使用此功能，并查看工具提示中的警告。 您也可能会看到其他警告。 移动指针不能还原到以前的应用程序状态的应用程序。

1. 按**F5**继续运行该应用程序。

    恭喜你完成本教程！

## <a name="next-steps"></a>后续步骤

在本教程中，已学习了如何启动调试器，单步执行代码，并检查变量。 您可能想要深入了解调试器功能，此外还提供详细信息链接。

> [!div class="nextstepaction"]
> [调试器功能简介](../debugger/debugger-feature-tour.md)
