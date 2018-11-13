---
title: 教程： 调试托管和本机代码 （混合模式）
description: 了解如何调试使用混合模式调试的.NET Core 或.NET Framework 应用程序中的本机 DLL
ms.custom: ''
ms.date: 11/02/2018
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
ms.openlocfilehash: 121584611dcf0f25fa1f32a616253ecdecf04332
ms.sourcegitcommit: 0a8ac5f2a685270d9ca79bb39d26fd90099bfa29
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2018
ms.locfileid: "51295756"
---
# <a name="tutorial-debug-managed-and-native-code-in-the-same-debugging-session"></a>教程： 在同一个调试会话中调试托管和本机代码

Visual Studio，您可以在调试会话，这称为混合模式调试中启用多个调试器类型。 在本教程中，了解如何在单一的调试会话中调试托管和本机代码。 

本教程演示如何调试托管应用中的本机代码，但也可以[调试托管的代码的本机应用](../debugger/how-to-debug-in-mixed-mode.md)。 调试器还支持其他类型的混合模式调试中，如调试[Python 和本机代码](../python/debugging-mixed-mode-c-cpp-python-in-visual-studio.md)，并在应用程序类型，如 ASP.NET 中使用脚本调试器。

在本教程中，你将：

> [!div class="checklist"]
> * 创建简单的本机 DLL
> * 创建用于调用 DLL 的简单.NET Core 或.NET Framework 的应用
> * 配置混合模式调试
> * 启动调试器
> * 命中的托管应用中的断点
> * 单步执行本机代码

## <a name="prerequisites"></a>系统必备

必须具有 Visual Studio 一并安装以下工作负荷：
- **使用 c + + 的桌面开发**
- 任一 **.NET 桌面开发**或 **.NET Core 跨平台开发**，取决于你想要创建哪种类型的应用程序。

如果未安装 Visual Studio，请转到 [Visual Studio 下载](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) 页免费安装。

如果已安装 Visual Studio，但没有需要选择的工作负荷**打开 Visual Studio 安装程序**Visual Studio 的左窗格中**新项目**对话框。 在 Visual Studio 安装程序中，选择工作负荷也需要并选择**修改**。

## <a name="create-a-simple-native-dll"></a>创建简单的本机 DLL

**若要创建 DLL 项目的文件：**

1. 在 Visual Studio 中，选择**文件** > **新建** > **项目**。

1. 在**新的项目**对话框中的**Visual c + +**，选择**其他**，然后选择**空项目**在中间窗格中。

1. 在中**名称**字段中，键入**Mixed_Mode_Debugging**，然后选择**确定**。

   Visual Studio 创建空项目并将其显示在**解决方案资源管理器**。

1. 在中**解决方案资源管理器**，选择**源文件**，然后选择**项目** > **添加新项**。 或者，右键单击**源文件**，然后选择**添加** > **新项**。 

1. 在中**新项**对话框中，选择**c + + 文件 (.cpp)**。 类型**Mixed_Mode.cpp**中**名称**字段，然后再选择**添加**。

    Visual Studio 将添加到新的 c + + 文件**解决方案资源管理器**。

1. 以下代码复制到*Mixed_Mode.cpp*:

    ```cpp
    #include "Mixed_Mode.h"
    ```
1. 在中**解决方案资源管理器**，选择**头文件**，然后选择**项目** > **添加新项**。 或者，右键单击**标头文件**，然后选择**添加** > **新项**。 

1. 在中**新项**对话框中，选择**标头文件 (.h)**。 类型**Mixed_Mode.h**中**名称**字段，然后再选择**添加**。

   Visual Studio 将添加到新的头文件**解决方案资源管理器**。

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

1. 选择**文件** > **全部保存**或按**Ctrl**+**Shift**+**S**用于保存的文件。

**若要配置和生成 DLL 项目：**

1. 在 Visual Studio 工具栏中，选择**调试**配置和**x86**或**x64**平台。 如果调用，应用将.NET Core，始终运行在 64 位模式下，选择**x64**作为平台。

1. 在中**解决方案资源管理器**，选择**Mixed_Mode_Debugging**项目节点，然后选择**属性**图标，或右键单击项目节点，然后选择**属性**。

1. 在顶部**属性**窗格中，请确保**配置**设置为**active （debug)** 并**平台**与你相同在工具栏中设置： **x64**，或**Win32**适用于 x86 平台。 

   > [!IMPORTANT]
   > 如果切换来自平台**x86**到**x64**或反之，则必须重新配置新的平台的属性。 

1. 下**配置属性**在左窗格中，选择**链接器** > **高级**，并在下拉列表中下一步**无入口点**，选择**否**。 如果您必须将其更改为**否**，选择**应用**。

1. 下**配置属性**，选择**常规**，并在下拉列表中下一步**配置类型**，选择**动态库 (.dll)**. 选择**Apply**，然后选择**确定**。

   ![切换到本机 DLL](../debugger/media/mixed-mode-set-as-native-dll.png)

1. 选择中的项目**解决方案资源管理器**，然后选择**构建** > **生成解决方案**，按**F7**，或右键单击该项目并选择**生成**。

   项目应顺利生成，没有错误。

## <a name="create-a-simple-managed-app-to-call-the-dll"></a>创建简单的托管应用程序调用 DLL

1. 在 Visual Studio 中，选择**文件** > **新建** > **项目**。

   > [!NOTE]
   > 尽管您还可以为现有的 c + + 解决方案添加新的托管的项目，创建一个新的解决方案支持更多的调试方案。

1. 在中**新的项目**对话框中，选择**Visual C#** ，然后在中间窗格中：

   - 对于.NET Framework 应用中，选择**控制台应用 (.NET Framework)**。
   
   - 对于.NET Core 应用，选择**控制台应用 (.NET Core)**。

1. 在中**名称**字段中，键入**Mixed_Mode_Calling_App**，然后选择**确定**。

   Visual Studio 创建空项目并将其显示在**解决方案资源管理器**。

1. 中的所有代码替换都为*Program.cs*使用以下代码：

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

1. 在新的代码中，将为中的文件路径`[DllImport]`替换为在文件路径*Mixed_Mode_Debugging.dll*你刚刚创建。 请参阅代码注释的提示。 请务必替换*用户名*占位符。

1. 选择**文件** > **保存 Program.cs**或按**Ctrl**+**S**保存该文件。

## <a name="configure-mixed-mode-debugging"></a>配置混合模式调试 

### <a name="to-configure-mixed-mode-debugging-for-a-net-framework-app"></a>若要配置混合模式调试的.NET Framework 应用 

1. 在中**解决方案资源管理器**，选择**Mixed_Mode_Calling_App**项目节点，然后选择**属性**图标，或右键单击项目节点，然后选择**属性**。

1. 选择**调试**在左窗格中，选择**启用本机代码调试**复选框，，然后关闭属性页以保存所做的更改。

    ![启用混合的模式调试](../debugger/media/mixed-mode-enable-native-code-debugging.png)

### <a name="to-configure-mixed-mode-debugging-for-a-net-core-app"></a>若要配置混合模式调试.NET Core 应用 

在大多数版本的 Visual Studio 2017，你必须使用*launchSettings.json*文件而不是项目属性以启用混合模式调试的.NET Core 应用中的本机代码。 若要跟踪此功能的 UI 更新，请参阅此[GitHub 问题](https://github.com/dotnet/project-system/issues/1125)。

1. 在中**解决方案资源管理器**，展开**属性**，然后打开*launchSettings.json*文件。 

   >[!NOTE]
   >默认情况下*launchSettings.json*处于*C:\Users\username\source\repos\Mixed_Mode_Calling_App\Properties*。 如果*launchSettings.json*不存在，请选择**Mixed_Mode_Calling_App**项目**解决方案资源管理器**，然后选择**属性**图标，或右键单击该项目并选择**属性**。 进行临时更改**调试**选项卡，并生成项目。 这将创建*launchSettings.json*文件。 还原在中所做的更改**调试**选项卡。

1. 在中*lauchsettings.json*文件中，添加以下行：

    ```csharp
    "nativeDebugging": true
    ```

    完整的文件将如下面的示例所示：

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

## <a name="set-a-breakpoint-and-start-debugging"></a>设置断点并开始调试

1. 在C#项目中，打开*Program.cs*。 通过最左边距中单击，选择行并按以下代码行上设置断点**F9**，或右键单击行，然后选择**断点** >  **插入断点**。

    ```csharp
    int result = Multiply(7, 7);
    ```

    设置了断点的左边距中显示一个红色圆圈。

1. 按**F5**，在 Visual Studio 工具栏中，选择绿色箭头，或选择**调试** > **开始调试**开始调试。

   您设置的断点处暂停调试器。 黄色箭头指示调试器当前暂停。

## <a name="step-in-and-out-of-native-code"></a>本机代码和缩小的步骤

1. 在调试托管应用中暂停时，按**F11**，或选择**调试** > **单步执行**。

   *Mixed_Mode.h*本机头文件将打开，并且看到调试器暂停的位置的黄色箭头。

   ![单步执行本机代码](../debugger/media/mixed-mode-step-into-native-code.png)

1. 现在，可以设置并命中断点并检查在本机或托管代码中的变量。

   - 悬停在变量中的源代码，以查看它们的值。

   - 查看变量和其值在**自动**并**局部变量**windows。

   - 在调试器中暂停时，还可以使用**Watch** windows 和**调用堆栈**窗口。

1. 按**F11**再次以前进调试器一个行。

1. 按**Shift**+**F11**或选择**调试** > **单步跳出**继续执行并再次在暂停托管的应用。

1. 按**F5**或选择绿色箭头以继续调试应用。

祝贺你！ 已完成本教程在混合模式调试。

## <a name="next-step"></a>下一步

在本教程中，您学习了如何通过启用混合模式调试来调试托管应用中的本机代码。 有关其他调试器功能的概述，请参阅：

> [!div class="nextstepaction"]
> [初探调试器](../debugger/debugger-feature-tour.md)
