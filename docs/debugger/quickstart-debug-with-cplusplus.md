---
title: 调试 c + +
description: 调试使用 Visual Studio 调试器的本机代码
ms.custom: mvc
ms.date: 03/18/2018
ms.technology: vs-ide-debug
ms.topic: quickstart
helpviewer_keywords:
- debugger
ms.assetid: 639e430b-6d2d-46bd-b738-8c60dfb384f1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 1027e5f737bf3fc75b33c47578ae0cc107a1fb7d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31926319"
---
# <a name="quickstart-debug-with-c-using-the-visual-studio-debugger"></a>快速入门： 使用 c + + 使用 Visual Studio 调试器进行调试

Visual Studio 调试器提供了许多功能强大的功能，以帮助你调试你的应用。 本主题提供了一种快速了解部分基本功能的方法。

## <a name="create-a-new-project"></a>创建新项目 

1. 在 Visual Studio 中，依次选择“文件”>“新建项目”。

2. 在“Visual C++”下，选择“Windows 桌面”，然后在中间窗格中选择“Windows 控制台应用程序”。

    如果看不到**Windows 控制台应用程序**项目模板中，单击**打开 Visual Studio 安装程序**中的左窗格中的链接，**新项目**对话框。 Visual Studio 安装程序启动。 选择**使用 c + + 桌面开发**工作负荷，然后选择**修改**。

3. 键入的名称，例如**MyDbgApp**单击**确定**。

    Visual Studio 随即创建项目。

4. 在 MyDbgApp.cpp 中，将以下代码

    ```c++
    int main()
    {
        return 0;
    }
    ```

    替换为此代码（请勿删除 `#include "stdafx.h"`）：

    ```c++
    #include <list>  
    #include <iostream>

    using namespace std;

    void doWork()
    {
        list <int> c1;

        c1.push_back(10);
        c1.push_back(20);

        const list <int> c2 = c1;
        const int &i = c2.front();
        const int &j = c2.front();
        cout << "The first element is " << i << endl;
        cout << "The second element is " << j << endl;

    }

    int main()
    {
        doWork();
    }
    ```

## <a name="set-a-breakpoint"></a>设置断点

A*断点*标记，它指示 Visual Studio 应在哪个位置挂起你运行代码，使你可以查看变量的值或内存，或确定是否运行代码的分支的行为。 它是在调试中的最基本功能。

1. 若要设置断点，请单击左侧的滚动条槽中`doWork`函数调用 (或选择行代码并按**F9**)。

    ![设置断点](../debugger/media/dbg-qs-set-breakpoint.png "设置断点")

2. 现在，按**F5** (或选择**调试 > 启动调试**)。

    ![命中断点](../debugger/media/dbg-qs-hit-breakpoint.png "命中断点")

    将断点设置调试器暂停。 由黄色箭头指示其中暂停调试器和应用程序执行的语句。 在行的`doWork`函数调用尚未执行。

    > [!TIP]
    > 如果你具有循环或递归中的存在断点，或者如果你有许多频繁单步执行时的断点使用[条件断点](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)若要确保你的代码仅在满足特定条件时挂起。 条件断点节省时间，并可以也更加轻松地调试难以重现的问题。

    当尝试调试内存相关故障 c + + 中的，你还可以使用断点检查地址值 （查找 NULL） 和引用计数。 

## <a name="navigate-code"></a>导航代码

有不同的命令，以指示调试器以继续。 我们显示 Visual Studio 2017 中有用的代码导航命令。

在暂停在断点处时，将鼠标悬停在该语句`c1.push_back(20)`直到绿色**运行单击**按钮![运行到单击](../debugger/media/dbg-tour-run-to-click.png "RunToClick")出现，，然后按**运行单击**按钮。

![单击运行](../debugger/media/dbg-qs-run-to-click.png "单击运行")

在应用继续执行，调用`doWork`，并在其中单击该按钮的代码行上暂停。

用于的常见键盘命令逐步调试代码包括**F10**和**F11**。 有关更多深入说明，请参阅[初学者指南](../debugger/getting-started-with-the-debugger.md)。

## <a name="inspect-variables-in-a-datatip"></a>检查在数据提示中的变量

1. 在当前行中 （由黄色执行指针标记） 的代码，将鼠标悬停在`c1`用鼠标以显示数据提示的对象。

    ![查看数据提示](../debugger/media/dbg-qs-data-tip.png "查看数据提示")

    数据提示显示的当前值`c1`变量，并允许您检查其属性。 在调试时，如果你看到在不希望一个值，你可能在代码的前面或调用行中出现了 bug。 

2. 展开以查看当前属性值的数据提示`c1`对象。

3. 如果你想要固定数据提示，以便你可以继续查看的值`c1`时执行代码时，单击小的图钉图标。 （你可以将移动固定数据提示到一个方便的位置。）

## <a name="edit-code-and-continue-debugging"></a>编辑代码，并继续调试

如果您确定你想要在你的代码在调试会话过程中测试更改，你可以这样做，太。

1. 单击第二个实例`c2.front()`和更改`c2.front()`到`c2.back()`。

2. 按**F10** (或**调试 > 逐过程**) 几次向前移动调试器和执行对编辑的代码。

    ![编辑并继续](../debugger/media/dbg-qs-edit-and-continue.gif "编辑并继续")

    **F10**函数而不是单步执行到它们 （仍执行，则跳过的代码） 通过推进处的时间，而步骤的调试器一个语句。

有关如何使用编辑并继续以及功能限制的详细信息，请参阅[编辑并继续](../debugger/edit-and-continue.md)。

## <a name="next-steps"></a>后续步骤

在本教程中，你已了解如何启动调试器，单步执行代码，并检查变量。 你可能想要获取高级查看调试器功能，以及指向详细信息。

> [!div class="nextstepaction"]
> [调试器功能简介](../debugger/debugger-feature-tour.md)
