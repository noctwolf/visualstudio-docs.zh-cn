---
title: 教程： 调试托管和本机代码 （混合模式）
description: 了解如何调试使用混合的模式调试的.NET Core 或.NET Framework 应用程序中的本机 DLL
ms.custom: ''
ms.date: 10/24/2018
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
ms.openlocfilehash: 97ad3b6e112a05db817f7a522c3865893d439fd7
ms.sourcegitcommit: 12d6398c02e818de4fbcb4371bae9e5db6cf9509
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2018
ms.locfileid: "50050321"
---
# <a name="tutorial-debug-managed-and-native-code-in-the-same-debugging-session"></a>教程： 在同一个调试会话中调试托管和本机代码

Visual Studio 允许你启用多个调试器类型在调试时，这称为混合的模式调试。 在本教程中，您可以设置选项来在单个的调试会话中调试托管和本机代码。 本教程演示如何调试托管应用中的本机代码，但你也可以执行与之相反，并[调试托管的代码的本机应用](../debugger/how-to-debug-in-mixed-mode.md)。 调试器还支持其他类型的混合的模式调试，如调试[Python 和本机代码](../python/debugging-mixed-mode-c-cpp-python-in-visual-studio.md)和在应用程序类型，如 ASP.NET 中使用脚本调试器。

在本教程中，你将：

> [!div class="checklist"]
> * 创建简单的本机 DLL
> * 创建用于调用 DLL 的简单.NET Core 或.NET Framework 的应用
> * 启动调试器
> * 命中的托管应用中的断点
> * 单步执行本机代码

## <a name="prerequisites"></a>系统必备

* 必须已安装的 Visual Studio 和**使用 c + + 的桌面开发**工作负荷。

    如果你尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 页免费安装。

    如果需要安装工作负载，但已有 Visual Studio，则单击“新建项目”对话框左窗格中的“打开 Visual Studio 安装程序”链接。 Visual Studio 安装程序启动。 选择“使用 C++ 的桌面开发”工作负载，然后选择“修改”按钮。

* 你还必须具有 **.NET 桌面开发**工作负荷或**跨平台开发的.NET Core**安装的工作负荷，根据哪些应用程序键入你想要创建。

## <a name="create-a-simple-native-dll"></a>创建简单的本机 DLL

1. 在 Visual Studio 中，选择**文件** > **新建** > **项目**。

1. 在中**新的项目**对话框框中，选择**Visual c + +**，**其他**从已安装的模板部分中，然后在中间窗格中选择**空项目**.

1. 在中**名称**字段中，键入**Mixed_Mode_Debugging**然后单击**确定**。

    Visual Studio 创建空的项目，在右窗格中将显示在解决方案资源管理器中。

1. 在解决方案资源管理器中右键单击**源文件**节点中 c + + 项目，，然后选择**添加** > **新项**，然后选择**c + +文件 (.cpp)**。 为文件名称**Mixed_Mode.cpp**，然后选择**添加**。

    Visual Studio 会添加新的 c + + 文件。

1. 以下代码复制到*Mixed_Mode.cpp*:

    ```cpp
    #include "Mixed_Mode.h"
    ```
1. 在解决方案资源管理器中右键单击**标头文件**节点中 c + + 项目，，然后选择**添加** > **新项**，然后选择**标头文件 (.h)**。 为文件名称**Mixed_Mode.h**，然后选择**添加**。

    Visual Studio 会添加新的头文件。

1. 以下代码复制到*Mixed_Mode.h*:

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

1. 从调试工具栏中，选择**调试**配置和**x86**或**x64**作为平台 (对于.NET Core，始终运行在 64 位模式下，选择**x64**作为平台)。

1. 在解决方案资源管理器中右键单击项目节点 (**Mixed_Mode_Debugging**)，然后选择**属性**。

    > [!IMPORTANT]
    > C + + 的属性配置为每个平台。 因此，如果切换介于 1 到其他 （x86 到 x64，反之亦然），还必须设置为新的配置属性。 (在属性页中，验证是否可以**x64**或**Win32**在页面顶部设置作为平台。)

1. 在中**属性**页上，选择**配置属性** > **链接器** > **高级**，和然后在**无入口点**下拉列表中，请确保**否**处于选中状态。 如果你需要将设置更改为**否**，然后选择**应用**。

1. 在中**属性**页上，选择**配置属性** > **常规**，然后选择**动态库 (.dll)** 从**配置类型**字段。 然后，应用设置。

    ![切换到本机 DLL](../debugger/media/mixed-mode-set-as-native-dll.png)

1. 右键单击项目并选择**生成**。

    项目应顺利生成，没有错误。

## <a name="create-a-simple-net-framework-or-net-core-app-to-call-the-dll"></a>创建简单的.NET Framework 或.NET Core 应用调用的 DLL

1. 在 Visual Studio 中，选择**文件** > **新建** > **项目**。

    > [!NOTE]
    > 尽管您还可以向 c + + 项目，而不是创建新的解决方案，该解决方案添加新的托管的项目不在这里，以支持大型数据集调试方案。

1. 选择用于你的应用程序代码的模板。

    用于.NET Framework 中**新的项目**对话框框中，选择**Visual C#**， **Windows 桌面**从已安装的模板部分中，然后在中间窗格中选择**控制台应用 (.NET Framework)**。

    有关.NET Core 中**新项目**对话框框中，选择**Visual C#**， **.NET Core**从已安装的模板部分中，然后在中间窗格中选择**控制台应用程序 （.NET Core）**。

1. 在中**名称**字段中，键入**Mixed_Mode_Calling_App**然后单击**确定**。

    Visual Studio 创建控制台项目，在右窗格中将显示在解决方案资源管理器中。

1. 在中*Program.cs*，默认代码替换为以下代码：

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
            // C:\Users\username\source\repos\Mixed_Mode_Debugging\x64\Debug\Mixed_Mode_Debugging.dll
            // Here, we show a typical path for a DLL targeting the **x86** option.
            [DllImport(@"C:\Users\username\source\repos\Mixed_Mode_Debugging\Debug\Mixed_Mode_Debugging.dll", EntryPoint =
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

1. 在新的代码中，对于以前创建 （请参阅代码注释） 的 DLL 更新到路径的文件路径。 请确保您替换*用户名*占位符。

## <a name="configure-mixed-mode-debugging-net-framework"></a>配置混合的模式调试 (.NET Framework)

1. 在解决方案资源管理器中右键单击托管**Mixed_Mode_Calling_App**项目，然后选择**设为启动项目**。

1. 右键单击托管**Mixed_Mode_Calling_App**项目，，然后选择**属性**，然后选择**调试**的左窗格中。 选择**启用本机代码调试**，然后关闭属性页以保存所做的更改。

    ![启用混合的模式调试](../debugger/media/mixed-mode-enable-native-code-debugging.png)

## <a name="configure-mixed-mode-debugging-net-core"></a>配置混合的模式调试 （.NET Core）

在大多数版本的 Visual Studio 2017，必须启用混合的模式调试中.NET Core 应用程序使用的本机代码*launchSettings.json*文件而不是**属性**页。 若要跟踪此功能的 UI 更新，请参阅此[GitHub 问题](https://github.com/dotnet/project-system/issues/1125)。

1. 打开*launchSettings.json*中的文件*属性*文件夹。 默认情况下，可以在以下位置找到该文件。

    *C:\Users\<用户名 > \source\repos\Mixed_Mode_Calling_App\Properties*

    如果该文件不存在，打开项目属性 (右键单击托管**Mixed_Mode_Calling_App**项目在解决方案资源管理器，然后选择**属性**)。 进行临时更改**调试**选项卡，并生成项目。 还原所做的更改。

1. 在中*lauchsettings.json*文件中，添加以下属性：

    ```csharp
    "nativeDebugging": true
    ```

    例如，因此，你的文件可能类似以下形式：

    ```csharp
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

1. 在 C# 项目中，打开*Program.cs*并通过在左边距中单击以下代码行中设置断点：

    ```csharp
    int result = Multiply(7, 7);
    ```

    若要指示设置了断点的左边距中显示一个红色圆圈。

1. 按**F5** (**调试** > **开始调试**) 以启动调试器。

    您设置的断点处暂停调试器。 黄色箭头指示调试器当前暂停。

## <a name="step-into-native-code"></a>单步执行本机代码

1. 在托管应用中暂停时，按**F11** (**调试** > **单步执行**)。

    与本机代码的头文件将打开并查看其中暂停调试器的黄色箭头。

    ![单步执行本机代码](../debugger/media/mixed-mode-step-into-native-code.png)

    现在，可以执行诸如设置并命中断点并检查变量。

1. 将鼠标悬停以查看其值的变量。

1. 看看**自动**并**局部变量**窗口，以查看变量和它们的值。

    在调试器中暂停时，您可以使用如其他调试器功能**Watch**窗口和**调用堆栈**窗口。

1. 按**F11**再次以前进调试器一个行。

1. 按**Shift + F11** (**调试** > **单步跳出**) 继续应用执行并再次暂停托管应用中。

1. 按 F5 继续。

    祝贺你！ 已完成本教程在混合的模式调试。

## <a name="next-steps"></a>后续步骤

在本教程中，您学习了如何通过启用混合的模式调试来调试托管应用中的本机代码。 其他调试器功能的概述，请参阅以下文章：

> [!div class="nextstepaction"]
> [初探调试器](../debugger/debugger-feature-tour.md)
