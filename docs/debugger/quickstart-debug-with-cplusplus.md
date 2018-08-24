---
title: 调试 c + +
description: 调试本机代码中使用 Visual Studio 调试器
ms.custom: mvc
ms.date: 08/06/2018
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
ms.openlocfilehash: 036774134f705d95fbc526a9e6a336ac43005820
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "39639771"
---
# <a name="quickstart-debug-with-c-using-the-visual-studio-debugger"></a>快速入门： 使用 c + + 使用 Visual Studio 调试器进行调试

Visual Studio 调试器提供了许多强大的功能以帮助您调试您的应用程序。 本主题提供了一种快速了解部分基本功能的方法。

## <a name="create-a-new-project"></a>创建新项目 

1. 在 Visual Studio 中，依次选择“文件”>“新建项目”。

2. 在“Visual C++”下，选择“Windows 桌面”，然后在中间窗格中选择“Windows 控制台应用程序”。

    如果没有看到**Windows 控制台应用程序**项目模板，请单击**打开 Visual Studio 安装程序**的左窗格中的链接**新项目**对话框。 Visual Studio 安装程序启动。 选择**使用 c + + 的桌面开发**工作负荷中，然后选择**修改**。

3. 键入一个名称，如**MyDbgApp**然后单击**确定**。

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

一个*断点*是一种标记，指示 Visual Studio 应在其中挂起你运行代码，使您可以看看变量值或内存，或是否运行代码的分支的行为。 它是在调试最基本的功能。

1. 若要设置断点，请单击左侧的滚动条槽中`doWork`函数调用 (或选择代码行并按**F9**)。

    ![设置断点](../debugger/media/dbg-qs-set-breakpoint.png "设置断点")

2. 现在，按**F5** (或选择**调试 > 启动调试**)。

    ![命中断点](../debugger/media/dbg-qs-hit-breakpoint.png "命中断点")

    调试器暂停设置了断点。 由黄色箭头指示其中暂停调试程序和应用执行的语句。 在行的`doWork`函数调用具有尚未执行。

    > [!TIP]
    > 如果在循环或递归中，断点，或如果你有很多断点的频繁单步执行时，使用[条件断点](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)以确保仅在满足特定条件时，暂停你的代码。 条件断点节省时间，还可更加容易地调试难以再现的问题。

    当尝试调试 c + + 中与内存相关的故障，您还可以使用断点来检查地址值 （查找 NULL） 和引用计数。 

## <a name="navigate-code"></a>导航代码

有不同的命令，以指示调试器才能继续。 我们将展示 Visual Studio 2017 中新增的一个有用的代码导航命令。

在断点处暂停时，将鼠标悬停在过程执行语句`c1.push_back(20)`直到绿色**运行时单击**按钮![运行时单击](../debugger/media/dbg-tour-run-to-click.png "RunToClick")出现，，然后按**运行时单击**按钮。

![运行时单击](../debugger/media/dbg-qs-run-to-click.png "运行时单击")

在应用继续执行，调用`doWork`，并单击该按钮的位置的代码行上暂停。

常见键盘命令，用于单步执行代码包括**F10**并**F11**。 有关更多深入说明，请参阅[初学者指南](../debugger/getting-started-with-the-debugger.md)。

## <a name="inspect-variables-in-a-datatip"></a>检查在数据提示中的变量

1. 在当前行 （由黄色执行指针标记） 的代码中，将鼠标悬停`c1`用鼠标以显示数据提示中的对象。

    ![查看数据提示](../debugger/media/dbg-qs-data-tip.png "查看数据提示")

    数据提示显示的当前值`c1`变量，并允许您检查其属性。 在调试时，如果你看到你不希望一个值，您可能在前面或调用行代码中出现了 bug。 

2. 展开以查看当前属性值的数据提示`c1`对象。

3. 如果你想要固定数据提示，以便可以继续查看的值`c1`时执行代码，请单击小图钉图标。 （您可以移动固定数据提示到一个方便的位置。）

## <a name="edit-code-and-continue-debugging"></a>编辑代码并继续调试

如果确定你想要测试调试会话期间在代码中的更改，您可以这样做，过。

1. 单击第二个实例`c2.front()`并更改`c2.front()`到`c2.back()`。

2. 按**F10** (或**调试 > 单步跳过**) 几次推进调试器进度和执行对编辑的代码。

    ![编辑并继续](../debugger/media/dbg-qs-edit-and-continue.gif "编辑并继续")

    **F10**函数而不是单步执行它们 （仍执行，则跳过的代码） 通过前移时间，但步骤调试器一个语句。

使用编辑并继续和功能限制的详细信息，请参阅[编辑并继续](../debugger/edit-and-continue.md)。

## <a name="next-steps"></a>后续步骤

在本教程中，已学习了如何启动调试器，单步执行代码，并检查变量。 您可能想要深入了解调试器功能，此外还提供详细信息链接。

> [!div class="nextstepaction"]
> [调试器功能简介](../debugger/debugger-feature-tour.md)
