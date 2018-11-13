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
# <a name="quickstart-debug-with-c-using-the-visual-studio-debugger"></a>快速入门： 使用 Visual Studio 调试器调试 c + + 

Visual Studio 调试器提供了许多强大的功能以帮助您调试您的应用程序。 本主题提供了学习一些基本功能的快速方法。

## <a name="create-a-new-project"></a>创建新项目 

1. 在 Visual Studio 中，依次选择“文件”>“新建项目”。

2. 在“Visual C++”下，选择“Windows 桌面”，然后在中间窗格中选择“Windows 控制台应用程序”。

    如果没有看到**Windows 控制台应用程序**项目模板，请单击**新建项目**对话框左窗格中的**打开 Visual Studio 安装程序**链接。 启动 Visual Studio 安装程序。 选择**使用 c ++ 的桌面开发**，然后选择**修改**。

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

一个*断点*是一种标记，指示 Visual Studio 应在其中挂起你正在运行的代码，使您可以查看变量的值或内存的行为，或某部分代码是否运行。 这是调试中最基本的功能。


1. 若要设置断点，请单击`doWork`函数调用左侧的滚动条 (或选择代码行并按**F9**)。

    ![设置断点](../debugger/media/dbg-qs-set-breakpoint.png "设置断点")

2. 现在，按**F5** (或选择**调试 > 启动调试**)。

    ![命中断点](../debugger/media/dbg-qs-hit-breakpoint.png "命中断点")

    调试器会在您设置断点的位置暂停。 调试器和应用程序运行暂停的语句由黄色箭头指示。 调用 doWork 函数的这行代码尚未执行。

    > [!TIP]
    > 如果你在循环或递归中使用断点，或者有许多断点经常单步执行，请使用[条件断点](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)以确保仅在满足特定条件时暂停代码。 条件断点可以节省时间，还可以更轻松地调试难以重现的问题。

    当尝试调试 c + + 中与内存相关的故障，您还可以使用断点来检查地址值 （查找 NULL） 和引用计数。 

## <a name="navigate-code"></a>导航代码

有不同的命令来指示调试器继续。 我们将展示 Visual Studio 2017 中新增的一个有用的代码导航命令。

在断点处暂停时，将鼠标悬停在语句`c1.push_back（20）`上，直到绿色**运行单击**按钮![运行单击](../debugger/media/dbg-tour-run-to-click.png "RunToClick")出现，，然后按**运行单击**按钮。

![运行时单击](../debugger/media/dbg-qs-run-to-click.png "运行时单击")

应用程序继续执行，调用`doWork`，并在单击该按钮的位置的代码行上暂停。


用于单步执行代码的常用键盘命令包括**F10**和**F11**。 有关更深入的说明，请参阅初学者指南](../debugger/getting-started-with-the-debugger.md)。

## <a name="inspect-variables-in-a-datatip"></a>检查数据提示中的变量

1. 在当前代码行中（由黄色执行指针标记），用鼠标将鼠标悬停在`c1`对象上以显示数据提示。


    ![查看数据提示](../debugger/media/dbg-qs-data-tip.png "查看数据提示")

    数据提示显示`c1`变量的当前值，并允许您检查其属性。 在调试时，如果你看到一个你不期望的值，你可能在前面或在调用的代码行中有一个 bug。


2. 展开数据提示以查看`c1`对象的当前属性值。

3. 如果要固定数据提示以便在执行代码时可以继续查看`c1`的值，请单击小图钉图标。 （您可以将固定的数据提示移动到方便的位置。）


## <a name="edit-code-and-continue-debugging"></a>编辑代码并继续调试

如果在调试会话期间您确定要在代码中测试更改，您可以这样做。

1. 单击`c2.front()`的第二个实例，并更改`c2.front()`为`c2.back()`。

2. 按**F10** (或**调试 > 单步跳过**) 几次以推进调试器并执行编辑过的代码。

    ![编辑并继续](../debugger/media/dbg-qs-edit-and-continue.gif "编辑并继续")

    **F10**一次向调试器推进一个语句，但是跳过函数而不是单步执行它们（跳过的代码仍然执行）。


有关使用编辑 - 继续和功能限制的详细信息，请参阅[编辑并继续](../debugger/edit-and-continue.md)。

## <a name="next-steps"></a>后续步骤

在本教程中，您学习了如何启动调试器，逐步执行代码以及检查变量。 您可能希望深入了解调试器功能以及指向更多信息的链接。

> [!div class="nextstepaction"]
> [调试器功能简介](../debugger/debugger-feature-tour.md)
