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
# <a name="quickstart-debug-with-managed-code-using-the-visual-studio-debugger"></a>快速入门：使用 Visual Studio 调试器借助托管代码进行调试

Visual Studio 调试器提供了许多有助于调试应用的强大功能。本主题提供了解部分基本功能的快速方法。

## <a name="create-a-new-project"></a>创建新项目 

1. 在 Visual Studio 中，依次选择“文件”>“新建项目”。

2. 在“Visual C＃”或“Visual Basic”下，选择 “.NET Core”，然后在中间窗格中选择“控制台应用(.NET Core)”。

     如果没有看到“控制台应用(.NET Core)”项目模板，请单击“新建项目”对话框左侧窗格中的“打开 Visual Studio 安装程序”链接。Visual Studio 安装程序随即启动。 选择“.NET 桌面开发”和“.NET Core”工作负荷，然后选择“修改”。
     
3. 键入一个名称，如**MyDbgApp**然后单击**确定**。

    Visual Studio 随即创建项目。

4. 在 Program.cs 或 Module1.vb 中，替换以下代码

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
    > 在 Visual Basic 中，确保将启动对象设置为 `Sub Main`（“属性”>“应用程序”>“启动对象”）

## <a name="set-a-breakpoint"></a>设置断点

一个“断点”就是一个标记，指示 Visual Studio 应在何处挂起正在运行的代码，以便你可以查看变量的值或内存的行为，或某部分代码是否已运行。这是调试中最基本的功能。

1. 若要设置断点，请单击 `doWork` 函数调用左侧的滚动条（或选择代码行并按 F9）。

    ![设置断点](../debugger/media/dbg-qs-set-breakpoint-csharp.png "设置断点")

2. 现在，按**F5** (或选择**调试 > 启动调试**)。

    ![命中断点](../debugger/media/dbg-qs-hit-breakpoint-csharp.png "命中断点")

    调试器会在设置断点的位置暂停。调试器和应用运行暂停时所在的语句用黄色箭头指示。具有 `doWork` 函数调用的代码行尚未执行。

    > [!TIP]
    > 如果在循环或递归中使用断点，或者有许多频繁单步执行的断点，请使用[条件断点](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)以确保仅在满足特定条件时暂停代码。条件断点可以节省时间，还可以更轻松地调试难以重现的问题。

## <a name="navigate-code"></a>导航代码

可使用不同的命令指示调试器继续运行。我们将展示 Visual Studio 2017 中新增的一个有用的代码导航命令。

在断点处暂停时，将鼠标悬停在语句 `c1.AddLast(20)` 上，直到绿色“运行时单击”按钮 ![运行时单击](../debugger/media/dbg-tour-run-to-click.png "RunToClick") 出现，，然后按“运行时单击”按钮。

![运行时单击](../debugger/media/dbg-qs-run-to-click-csharp.png "运行时单击")

应用将继续执行并调用 `doWork`，然后在单击该按钮时所在的代码行上暂停。

用于单步执行代码的常用键盘命令包括 F10 和 F11。有关更深入的说明，请参阅初学者指南](../debugger/getting-started-with-the-debugger.md)。

## <a name="inspect-variables-in-a-datatip"></a>检查数据提示中的变量

1. 在当前代码行中（用黄色执行指针标记），将鼠标悬停在 `c1` 对象上以显示数据提示。

    ![查看数据提示](../debugger/media/dbg-qs-data-tip-csharp.png "查看数据提示")

    数据提示可显示 `c1` 变量的当前值，你还可以检查其属性。在调试时，如果看到意外值，则之前或当前调用的代码行中可能存在 bug。 

2. 展开数据提示以查看`c1`对象的当前属性值。

3. 如果要固定数据提示以便在执行代码时可以继续查看 `c1` 的值，请单击小图钉图标。（可以将固定的数据提示移动到便于访问的位置。）

## <a name="edit-code-and-continue-debugging"></a>编辑代码并继续调试

如果在调试会话期间发现了要进行测试的更改，你也可以这样做。

1. 单击 `c2.First.Value` 的第二个实例并将 `c2.First.Value` 更改为 `c2.Last.Value`。

2. 按 F10（或“调试”>“单步跳过”）几次以推进调试器并执行编辑过的代码。

    ![编辑并继续](../debugger/media/dbg-qs-edit-and-continue-csharp.gif "编辑并继续")

    F10 一次可向调试器推进一个语句，但会单步跳过函数而不是单步执行它们（跳过的代码仍将执行）。

有关使用“编辑并继续”和功能限制的详细信息，请参阅[编辑并继续](../debugger/edit-and-continue.md)。

## <a name="next-steps"></a>后续步骤

本教程介绍了如何启动调试器、单步执行代码以及检查变量。如需深入了解调试器功能，请通过以下链接了解详细信息。

> [!div class="nextstepaction"]
> [调试器功能简介](../debugger/debugger-feature-tour.md)
