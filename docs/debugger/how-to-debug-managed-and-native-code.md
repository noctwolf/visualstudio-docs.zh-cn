---
title: 教程： 调试托管和本机代码 |Microsoft 文档
description: 了解如何调试.NET Core 或.NET Framework 应用程序中的本机 DLL
ms.custom: ''
ms.date: 04/27/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
dev_langs:
- CSharp
- C++
helpviewer_keywords:
- mixed mode debugging
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
- cplusplus
ms.openlocfilehash: d8987d24a6302c9d9ffd7ffdb127e52c57e22ff9
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "34764548"
---
# <a name="tutorial-debug-managed-and-native-code-in-visual-studio"></a>教程： 调试 Visual Studio 中的托管和本机代码

Visual Studio 允许你启用多个调试器类型在调试时，这称为混合的模式调试。 在本教程中，你可以设置选项以在单个的调试会话中调试托管和本机代码。 本教程演示如何调试托管应用中的本机代码，但你还可以执行反向，和[调试托管的代码的本机应用](../debugger/how-to-debug-in-mixed-mode.md)。 调试器还支持其他类型的混合的模式调试，例如调试[Python 和本机代码](../python/debugging-mixed-mode-c-cpp-python-in-visual-studio.md)以及在应用程序类型，如 ASP.NET 中使用脚本调试器。

在本教程中，你将：

> [!div class="checklist"]
> * 创建简单的本机 DLL
> * 创建用于调用 DLL 的简单.NET Core 或.NET Framework 的应用
> * 启动调试器
> * 在命中断点的托管应用
> * 单步执行本机代码

## <a name="prerequisites"></a>系统必备

* 你必须安装 Visual Studio 和**使用 c + + 桌面开发**工作负荷。

    如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)页免费安装。

    如果需要安装工作负载，但已有 Visual Studio，则单击“新建项目”对话框左窗格中的“打开 Visual Studio 安装程序”链接。 Visual Studio 安装程序启动。 选择“Node.js 开发”工作负载，然后选择“修改”。

* 你还必须具有 **.NET 桌面开发**工作负荷或**跨平台开发的.NET Core**安装的工作负荷，根据哪些应用程序键入你想要创建。

## <a name="create-a-simple-native-dll"></a>创建简单的本机 DLL

1. 在 Visual Studio 中，选择**文件** > **新建** > **项目**。

1. 在**新项目**对话框框中，选择**Visual c + +**，**常规**从已安装的模板部分中，然后在中间窗格中选择**空项目**.

1. 在**名称**字段中，键入**混合模式调试**单击**确定**。

    Visual Studio 创建空的项目，在右窗格中显示在解决方案资源管理器。

1. 在解决方案资源管理器，右键单击**源文件**节点在 c + + 项目，，然后选择**添加** > **新项**，然后选择**c + +文件 (.cpp)**。 将文件命名**混合 Mode.cpp**，然后选择**添加**。

    Visual Studio 将添加新的 c + + 文件。

1. 下面的代码复制到*混合 Mode.cpp*:

    ```cpp
    #include "Mixed_Mode.h"
    ```
1. 在解决方案资源管理器，右键单击**标头文件**节点在 c + + 项目，，然后选择**添加** > **新项**，然后选择**标头文件 (.h)**。 将文件命名**混合 Mode.h**，然后选择**添加**。

    Visual Studio 将添加新的头文件。

1. 下面的代码复制到*混合 Mode.h*:

    ```cpp
    #ifndef MIXED_MODE_MULTIPLY_HPP
    #define MIXED_MODE_MULTIPLY_HPP

    extern "C"
    {
        __declspec(dllexport) int __stdcall mixed_mode_multiply(int a, int b) {
            return a * b;
        }
    }
    #endif
    ```

1. 从调试工具栏中，选择**调试**配置和**任意 CPU**作为平台，或者，对于.NET Core，选择**x64**作为平台。

    > [!NOTE]
    > 在.NET Core 上选择**x64**作为平台。 因此，这是必需的.NET Core 始终运行在 64 位模式下。

1. 在解决方案资源管理器，右键单击项目节点 (**混合模式调试**)，然后选择**属性**。

1. 在**属性**页上，选择**配置属性** > **链接器** > **高级**，和然后在**无入口点**下拉列表中，选择**否**。 然后应用设置。

1. 在**属性**页上，选择**配置属性** > **常规**，然后选择**动态库 (.dll)** 从**配置类型**字段。 然后应用设置。

    ![切换到本机 DLL](../debugger/media/mixed-mode-set-as-native-dll.png)

1. 右键单击项目并选择**调试** > **生成**。

    项目应顺利生成，没有错误。

## <a name="create-a-simple-net-framework-or-net-core-app-to-call-the-dll"></a>创建简单的.NET Framework 或.NET Core 应用调用的 DLL

1. 在 Visual Studio 中，选择**文件** > **新建** > **项目**。

1. 选择为你的应用程序代码的模板。

    对于.NET Framework，在**新项目**对话框框中，选择**Visual C#**， **Windows 桌面**从已安装的模板部分中，然后在中间窗格中选择**控制台应用程序 (.NET Framework)**。

    有关.NET Core 中**新项目**对话框框中，选择**Visual C#**， **.NET Core**从已安装的模板部分中，然后在中间窗格中选择**控制台应用程序 （.NET Core）**。

1. 在**名称**字段中，键入**Mixed_Mode_Calling_App**单击**确定**。

    Visual Studio 创建控制台项目，在右窗格中显示在解决方案资源管理器。

1. 在*Program.cs*，将默认代码替换为以下代码：

    ```csharp
    using System;
    using System.Runtime.InteropServices;

    namespace Mixed_Mode_Calling_App
    {
        public class Program
        {
            // Replace the file path shown here with the
            // file path on your computer. For .NET Core, the typical (default) path
            // for a 64-bit DLL might look like this:
            // C:\Users\username\source\repos\Mixed-Mode-Debugging\x64\Debug\Mixed-Mode-Debugging.dll
            // Here, we show a typical path for a DLL targeting the **Any CPU** option.
            [DllImport(@"C:\Users\username\source\repos\Mixed-Mode-Debugging\Debug\Mixed-Mode-Debugging.dll", EntryPoint =
            "mixed_mode_multiply", CallingConvention = CallingConvention.StdCall)]
            public static extern int Multiply(int x, int y);
            public static void Main(string[] args)
            {
                int result = Multiply(7, 7);
                Console.WriteLine("The answer is {0}", result);
                Console.ReadKey();
            }
        }
    }
    ```

## <a name="configure-mixed-mode-debugging-net-framework"></a>配置混合的模式调试 (.NET Framework)

1. 在解决方案资源管理器，右键单击托管**Mixed_Mode_Calling_App**项目，选择**设为启动项目**。

1. 右键单击托管**Mixed_Mode_Calling_App**项目，，然后选择**属性**，然后选择**调试**的左窗格中。 选择**启用本机代码调试**，然后关闭属性页，以保存所做的更改。

    ![启用混合的模式调试](../debugger/media/mixed-mode-enable-native-code-debugging.png)

## <a name="configure-mixed-mode-debugging-net-core"></a>配置混合的模式调试 （.NET Core）

在大多数版本的 Visual Studio 2017，必须启用混合的模式调试中.NET Core 应用程序使用的本机代码*launchSettings.json*文件而不是**属性**页。 若要跟踪此功能的用户界面更新，请参阅此[GitHub 问题](https://github.com/dotnet/project-system/issues/1125)。

1. 打开*launchSettings.json*文件中*属性*文件夹。 默认情况下，你可以在此位置中找到该文件。

    *C:\Users\<用户名 > \source\repos\Mixed_Mode_Calling_App\Properties*

    如果文件不存在，打开项目属性 (右键单击托管**Mixed_Mode_Calling_App**项目在解决方案资源管理器，然后选择**属性**)。 进行临时更改在**调试**选项卡上和生成项目。 还原所做的更改。

1. 在*lauchsettings.json*文件中，添加以下属性：

    ```
    "nativeDebugging": true
    ```

    因此，例如，你的文件可能如下所示：

    ```
    {
      "profiles": {
        "Mixed_Mode_Calling_App": {
          "commandName": "Project",
          "nativeDebugging": true
        }
      }
    }
    ```

## <a name="set-a-breakpoint-and-start-the-debugger"></a>设置断点并启动调试器

1. 在 C# 项目中，打开*Program.cs*和以下代码行中设置断点，通过单击左边距中：

    ```csharp
    int result = Multiply(7, 7);
    ```

    以指示你设置了断点的左边距中显示一个红色圆圈。

1. 按**F5** (**调试** > **启动调试**) 以启动调试器。

    在你设置的断点处暂停调试器。 黄色箭头指示调试器当前暂停的位置。

## <a name="step-into-native-code"></a>单步执行本机代码

1. 在托管应用中暂停时，按**F11** (**调试** > **单步执行**)。

    与本机代码的头文件将打开并查看其中暂停调试器的黄色箭头。

    ![单步执行本机代码](../debugger/media/mixed-mode-step-into-native-code.png)

    现在，你可以执行诸如组和命中断点并检查变量。

1. 将鼠标悬停在变量上以查看它们的值。

1. 查看**自动**和**局部变量**窗口，以查看变量和它们的值。

    在暂停时在调试器中，你可以使用其他调试器功能如**监视**窗口和**调用堆栈**窗口。

1. 按**F11**再次继续调试器一个行。

1. 按**Shift + F11** (**调试** > **单步跳出**) 若要继续应用执行，托管应用中再次暂停。

1. 按 F5 继续。

    祝贺你！ 您已经完成本教程在混合的模式调试。

## <a name="next-steps"></a>后续步骤

在本教程中，您学习了如何通过启用混合的模式调试来调试托管应用中的本机代码。 其他调试器功能的概述，请参阅以下文章：

> [!div class="nextstepaction"]
> [初探调试器](../debugger/debugger-feature-tour.md)