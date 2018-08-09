---
title: 调试托管的代码 |Microsoft Docs
description: 调试 C# 或 Visual Basic 中使用 Visual Studio 调试器
ms.custom: mvc
ms.date: 03/18/2018
ms.technology: vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: f4cea2e1-08dc-47ac-aba2-3b8c338e607f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 2ba06156a8fa44a61b489deba6104673e8fb08ce
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39637518"
---
# <a name="quickstart-debug-with-managed-code-using-the-visual-studio-debugger"></a>快速入门： 使用托管代码使用 Visual Studio 调试器进行调试

Visual Studio 调试器提供了许多强大的功能以帮助您调试您的应用程序。 本主题提供了一种快速了解部分基本功能的方法。

## <a name="create-a-new-project"></a>创建新项目 

1. 在 Visual Studio 中，依次选择“文件”>“新建项目”。

2. 下**Visual C#** 或**Visual Basic**，选择 **.NET Core**，，然后在中间窗格中选择**控制台应用程序 (.NET Core)**。

     如果没有看到“控制台应用(.NET Core)”项目模板，请单击“新建项目”对话框左侧窗格中的“打开 Visual Studio 安装程序”链接。 Visual Studio 安装程序启动。 选择 **.NET 桌面开发**和 **.NET Core** 工作负荷，然后选择**修改**。

3. 键入一个名称，如**MyDbgApp**然后单击**确定**。

    Visual Studio 随即创建项目。

4. 在中*Program.cs*或*Module1.vb*，以下代码替换为

    ```csharp
    class Program
    {
        static void Main(string[] args)
        {
        }
    }
    ```

    ```vb
    Module Module1
        Sub Main()
        End Sub
    End Module
    ```

    替换为此代码：

    ```csharp
    class Program
    {
        private static void doWork()
        {
            LinkedList<int> c1 = new LinkedList<int>();

            c1.AddLast(10);
            c1.AddLast(20);

            LinkedList<int> c2 = new LinkedList<int>(c1);
            int i = c2.First.Value;
            int j = c2.First.Value;
            Console.Write("The first element is ");
            Console.Write(i);
            Console.Write("\n");
            Console.Write("The second element is ");
            Console.Write(j);
            Console.Write("\n");

        }

        static int Main()
        {
            // using namespace std;
            doWork();
            return 0;

        }
    }
    ```

    ```vb
    Imports System.Collections.Generic

    Namespace MyDbgApp
        Class Program
            Private Shared Sub doWork()
                Dim c1 As New LinkedList(Of Integer)()

                c1.AddLast(10)
                c1.AddLast(20)

                Dim c2 As New LinkedList(Of Integer)(c1)
                Dim i As Integer = c2.First.Value
                Dim j As Integer = c2.First.Value
                Console.Write("The first element is ")
                Console.Write(i)
                Console.Write(vbLf)
                Console.Write("The second element is ")
                Console.Write(j)
                Console.Write(vbLf)

            End Sub

            Public Shared Function Main() As Integer
                ' using namespace std;
                doWork()
                Return 0

            End Function
        End Class
    End Namespace
    ```

    > [!NOTE]
    > 在 Visual Basic 中，确保将启动对象设置为 `Sub Main`（“属性”>“应用程序”>“启动对象”）。

## <a name="set-a-breakpoint"></a>设置断点

一个*断点*是一种标记，指示 Visual Studio 应在其中挂起你运行代码，使您可以看看变量值或内存，或是否运行代码的分支的行为。 它是在调试最基本的功能。

1. 若要设置断点，请单击左侧的滚动条槽中`doWork`函数调用 (或选择代码行并按**F9**)。

    ![设置断点](../debugger/media/dbg-qs-set-breakpoint-csharp.png "设置断点")

2. 现在，按**F5** (或选择**调试 > 启动调试**)。

    ![命中断点](../debugger/media/dbg-qs-hit-breakpoint-csharp.png "命中断点")

    调试器暂停设置了断点。 由黄色箭头指示其中暂停调试程序和应用执行的语句。 在行的`doWork`尚未尚未执行函数调用。

    > [!TIP]
    > 如果在循环或递归中，断点，或如果你有很多断点的频繁单步执行时，使用[条件断点](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)以确保仅在满足特定条件时，暂停你的代码。 条件断点可以节省时间，它还可更加容易地调试难以再现的问题。

## <a name="navigate-code"></a>导航代码

有不同的命令，以指示调试器才能继续。 我们将展示 Visual Studio 2017 中新增的一个有用的代码导航命令。

在断点处暂停时，将鼠标悬停在过程执行语句`c1.AddLast(20)`直到绿色**运行时单击**按钮![运行时单击](../debugger/media/dbg-tour-run-to-click.png "RunToClick")出现，，然后按**运行时单击**按钮。

![运行时单击](../debugger/media/dbg-qs-run-to-click-csharp.png "运行时单击")

在应用继续执行，调用`doWork`，并单击该按钮的位置的代码行上暂停。

常见键盘命令，用于单步执行代码包括**F10**并**F11**。 有关更多深入说明，请参阅[初学者指南](../debugger/getting-started-with-the-debugger.md)。

## <a name="inspect-variables-in-a-datatip"></a>检查在数据提示中的变量

1. 在当前行 （由黄色执行指针标记） 的代码中，将鼠标悬停`c1`用鼠标以显示数据提示中的对象。

    ![查看数据提示](../debugger/media/dbg-qs-data-tip-csharp.png "查看数据提示")

    数据提示显示的当前值`c1`变量，并允许您检查其属性。 在调试时，如果你看到你不希望一个值，您可能在前面或调用行代码中出现了 bug。 

2. 展开以查看当前属性值的数据提示`c1`对象。

3. 如果你想要固定数据提示，以便可以继续查看的值`c1`时执行代码，请单击小图钉图标。 （您可以移动固定数据提示到一个方便的位置。）

## <a name="edit-code-and-continue-debugging"></a>编辑代码并继续调试

如果确定你想要测试调试会话期间在代码中的更改，您可以这样做，过。

1. 单击第二个实例`c2.First.Value`并更改`c2.First.Value`到`c2.Last.Value`。

2. 按**F10** (或**调试 > 单步跳过**) 几次推进调试器进度和执行对编辑的代码。

    ![编辑并继续](../debugger/media/dbg-qs-edit-and-continue-csharp.gif "编辑并继续")

    **F10**函数而不是单步执行它们 （仍执行，则跳过的代码） 通过前移时间，但步骤调试器一个语句。

使用编辑并继续和功能限制的详细信息，请参阅[编辑并继续](../debugger/edit-and-continue.md)。

## <a name="next-steps"></a>后续步骤

在本教程中，已学习了如何启动调试器，单步执行代码，并检查变量。 您可能想要深入了解调试器功能，此外还提供详细信息链接。

> [!div class="nextstepaction"]
> [调试器功能简介](../debugger/debugger-feature-tour.md)
