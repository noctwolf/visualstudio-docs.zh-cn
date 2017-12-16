---
title: "调试 Visual Studio 的 ASP.NET-|Microsoft 文档"
ms.custom: 
ms.date: 12/06/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: quickstart
helpviewer_keywords: debugger
ms.assetid: f4cea2e1-08dc-47ac-aba2-3b8c338e607f
caps.latest.revision: "1"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b0ba7735dd44d029889c57d151e6fba39ba7b2df
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="debug-aspnet-with-the-visual-studio-debugger"></a>使用 Visual Studio 调试器进行调试 ASP.NET

Visual Studio 调试器提供了许多功能强大的功能，以帮助你调试你的应用。 本主题提供的快速方法，若要了解的一些基本功能。

## <a name="create-a-new-project"></a>创建新项目 

1. 在 Visual Studio 中，选择**文件 > 新建项目**。

1. 下**Visual C#**，选择**Web**，，然后在中间窗格中选择**ASP.NET 核心 Web 应用程序**。

1. 键入的名称，例如**MyDbgApp**单击**确定**。

1. 在显示的对话框中，选择**Web 应用程序**在中间窗格中，然后单击**确定**。

     如果看不到**Web 应用程序**项目模板中，单击**打开 Visual Studio 安装程序**中的左窗格中的链接，**新项目**对话框。 Visual Studio 安装程序启动。 选择**ASP.NET**和**.NET 核心**工作负荷，然后选择**修改**。

    ![选择一个 Web 应用程序](../debugger/media/dbg-qs-aspnet-choose-web-app.png)

    Visual Studio 创建项目。

1. 在解决方案资源管理器，打开 About.cshtml.cs （在下 Pages/About.cshtml) 并将下面的代码

    ```c#
    public void OnGet()
    {
        Message = "Your application description page.";
    }
    ```

    替换为以下代码：

    ```c#
    public void OnGet()
    {
        LinkedList<int> result = doWork();
        Message = "Result of work: " + result.First.Value + ", " + result.First.Value;
    }

    private static LinkedList<int> doWork()
    {
        LinkedList<int> c1 = new LinkedList<int>();

        c1.AddLast(10);
        c1.AddLast(20);

        LinkedList<int> c2 = new LinkedList<int>(c1);

        return c2;

    }
    ```

## <a name="set-a-breakpoint"></a>设置断点

A*断点*标记，它指示 Visual Studio 应在哪个位置挂起你运行代码，使你可以查看变量的值或内存，或确定是否运行代码的分支的行为。 它是在调试中的最基本功能。

1. 若要设置断点，请单击左侧的滚动条槽中`doWork`函数 (或选择行代码并按**F9**)。

    ![设置断点](../debugger/media/dbg-qs-set-breakpoint-aspnet.png)

    断点设置为左侧的左大括号 (`{`)。

1. 现在，按**F5** (或选择**调试 > 启动调试**)。

1. 加载 web 页时单击**有关**web 页顶部的链接。

    将断点设置调试器暂停。 由黄色箭头指示其中暂停调试器和应用程序执行的语句。 在行的左大括号 (`{`) 后`doWork`函数声明尚未执行。

    ![命中断点](../debugger/media/dbg-qs-hit-breakpoint-aspnet.png)

    > [!TIP]
    > 如果你有循环或递归中的存在断点，或如果你有大量断点频繁单步执行，使用[条件断点](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)若要确保你的代码仅在满足特定条件时挂起。 这可以节省时间并可以还使其更轻松地调试难以重现的问题。

## <a name="navigate-code"></a>导航代码

有不同的命令，以指示调试器以继续。 我们将演示 Visual Studio 2017 中有用的代码导航命令。

- 在断点处暂停时，将鼠标悬停在该语句`return c2`直到绿色**运行单击**按钮![运行到单击](../debugger/media/dbg-tour-run-to-click.png)出现，，然后按**运行单击**按钮。

    ![单击运行](../debugger/media/dbg-qs-run-to-click-aspnet.png)

    应用程序继续执行，并在其中单击该按钮的代码行上暂停。

    用于的常见键盘命令逐步调试代码包括**F10**和**F11**。 有关更多深入说明，请参阅[初学者指南](../debugger/getting-started-with-the-debugger.md)。

## <a name="inspect-variables-in-a-datatip"></a>检查在数据提示中的变量

1. 在当前行中 （由黄色执行指针标记） 的代码，将鼠标悬停在`c2`用鼠标以显示数据提示的对象。

    ![查看数据提示](../debugger/media/dbg-qs-data-tip-aspnet.png)

    数据提示显示的当前值`c2`变量，并允许您检查其属性。 在调试时，如果你看到在不希望一个值，你可能在代码的前面或调用行中出现了 bug。 

2. 展开以查看当前属性值的数据提示`c2`对象。

3. 如果你想要固定数据提示，以便你可以继续查看的值`c2`时执行代码时，单击小的图钉图标。 （你可以将移动固定数据提示到一个方便的位置。）

## <a name="edit-code-and-continue-debugging"></a>编辑代码，并继续调试

如果您确定你想要在你的代码在调试会话过程中测试更改，你可以这样做，太。

1. 在`OnGet`方法中，单击第二个实例`result.First.Value`和更改`result.First.Value`到`result.Last.Value`。

1. 按**F10** (或**调试 > 逐过程**) 几次向前移动调试器和执行对编辑的代码。

    ![编辑并继续](../debugger/media/dbg-qs-edit-and-continue-aspnet.png "编辑并继续")

    **F10**函数而不是单步执行到它们 （仍执行，则跳过的代码） 通过推进处的时间，而步骤的调试器一个语句。

有关如何使用编辑并继续以及功能限制的详细信息，请参阅[编辑并继续](../debugger/edit-and-continue.md)。

## <a name="next-steps"></a>后续步骤

- 若要了解有关调试器的详细信息，请参阅[启动调试器，并导航代码](../debugger/getting-started-with-the-debugger.md)。
- 若要了解有关断点的详细信息，请参阅[使用断点](../debugger/using-breakpoints.md)。

## <a name="see-also"></a>另请参阅  
 [在 Visual Studio 中进行调试](../debugger/index.md)  
 [调试器功能简介](../debugger/debugger-feature-tour.md)
