---
title: 调试 ASP.NET
description: 调试 ASP.NET 使用 Visual Studio 调试器
ms.custom: mvc
ms.date: 08/06/2018
ms.technology: vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: f4cea2e1-08dc-47ac-aba2-3b8c338e607f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 74671401b3e3eaeae5840110dfc37c926266f98a
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39636982"
---
# <a name="quickstart-debug-aspnet-with-the-visual-studio-debugger"></a>快速入门： 使用 Visual Studio 调试器调试 ASP.NET

Visual Studio 调试器提供了许多强大的功能以帮助您调试您的应用程序。 本主题提供了一种快速了解部分基本功能的方法。

## <a name="create-a-new-project"></a>创建新项目 

1. 在 Visual Studio 中，依次选择“文件”>“新建项目”。

1. 下**Visual C#**，选择**Web**，，然后在中间窗格中选择**ASP.NET Core Web 应用程序**。

1. 键入一个名称，如**MyDbgApp**然后单击**确定**。

1. 在出现的对话框中，选择**Web 应用程序**在中间窗格中，然后单击**确定**。

     如果没有看到**Web 应用程序**项目模板，请单击**打开 Visual Studio 安装程序**的左窗格中的链接**新项目**对话框。 Visual Studio 安装程序启动。 选择“ASP.NET 和 web 开发”工作负载，然后选择“修改”。

    ![选择 Web 应用程序](../debugger/media/dbg-qs-aspnet-choose-web-app.png)

    Visual Studio 随即创建项目。

1. 在解决方案资源管理器，打开 About.cshtml.cs （在 pages/About.cshtml) 并将以下代码

    ```csharp
    public void OnGet()
    {
        Message = "Your application description page.";
    }
    ```

    替换为此代码：

    ```csharp
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

一个*断点*是一种标记，指示 Visual Studio 应在其中挂起你运行代码，使您可以看看变量值或内存，或是否运行代码的分支的行为。 它是在调试最基本的功能。

1. 若要设置断点，请单击左侧的滚动条槽中`doWork`函数 (或选择代码行并按**F9**)。

    ![设置断点](../debugger/media/dbg-qs-set-breakpoint-aspnet.png)

    断点设置为左侧的左大括号 (`{`)。

1. 现在，按**F5** (或选择**调试 > 启动调试**)。

1. 当在加载 web 页时，单击**有关**web 页顶部的链接。

    调试器暂停设置了断点。 由黄色箭头指示其中暂停调试程序和应用执行的语句。 在行的左大括号 (`{`) 后`doWork`函数声明具有尚未执行。

    ![命中断点](../debugger/media/dbg-qs-hit-breakpoint-aspnet.png)

    > [!TIP]
    > 如果在循环或递归中，断点，或如果你有很多断点的频繁单步执行时，使用[条件断点](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)以确保仅在满足特定条件时，暂停你的代码。 这可以节省时间，还可更加容易地调试难以再现的问题。

## <a name="navigate-code"></a>导航代码

有不同的命令，以指示调试器才能继续。 我们将展示 Visual Studio 2017 中新增的一个有用的代码导航命令。

在断点处暂停时，将鼠标悬停在过程执行语句`return c2`直到绿色**运行时单击**按钮![运行时单击](../debugger/media/dbg-tour-run-to-click.png)出现，，然后按**运行时单击**按钮。

![运行时单击](../debugger/media/dbg-qs-run-to-click-aspnet.png)

应用程序会继续执行，并单击该按钮的位置的代码行上暂停。

常见键盘命令，用于单步执行代码包括**F10**并**F11**。 有关更多深入说明，请参阅[初学者指南](../debugger/getting-started-with-the-debugger.md)。

## <a name="inspect-variables-in-a-datatip"></a>检查在数据提示中的变量

1. 在当前行 （由黄色执行指针标记） 的代码中，将鼠标悬停`c2`用鼠标以显示数据提示中的对象。

    ![查看数据提示](../debugger/media/dbg-qs-data-tip-aspnet.png)

    数据提示显示的当前值`c2`变量，并允许您检查其属性。 在调试时，如果你看到你不希望一个值，您可能在前面或调用行代码中出现了 bug。 

2. 展开以查看当前属性值的数据提示`c2`对象。

3. 如果你想要固定数据提示，以便可以继续查看的值`c2`时执行代码，请单击小图钉图标。 （您可以移动固定数据提示到一个方便的位置。）

## <a name="edit-code-and-continue-debugging"></a>编辑代码并继续调试

如果确定你想要测试调试会话期间在代码中的更改，您可以这样做，过。

1. 在中`OnGet`方法中，单击第二个实例`result.First.Value`并将更改`result.First.Value`到`result.Last.Value`。

1. 按**F10** (或**调试 > 单步跳过**) 几次推进调试器进度和执行对编辑的代码。

    ![编辑并继续](../debugger/media/dbg-qs-edit-and-continue-aspnet.png "编辑并继续")

    **F10**函数而不是单步执行它们 （仍执行，则跳过的代码） 通过前移时间，但步骤调试器一个语句。

使用编辑并继续和功能限制的详细信息，请参阅[编辑并继续](../debugger/edit-and-continue.md)。

## <a name="next-steps"></a>后续步骤

在本教程中，已学习了如何启动调试器，单步执行代码，并检查变量。 您可能想要深入了解调试器功能，此外还提供详细信息链接。

> [!div class="nextstepaction"]
> [调试器功能简介](../debugger/debugger-feature-tour.md)
