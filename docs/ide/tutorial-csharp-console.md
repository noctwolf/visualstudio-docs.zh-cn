---
title: Visual Studio 中的 C# 控制台应用程序入门
description: 了解如何在 Visual Studio 中分步创建 C# 控制台应用程序。
ms.custom: ''
ms.date: 09/28/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: ad1ee95cb9cc754261502e7377cde6c91e5befce
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2018
ms.locfileid: "47859505"
---
# <a name="tutorial-get-started-with-a-c-console-app-in-visual-studio"></a>教程：Visual Studio 中的 C# 控制台应用程序入门

在本 C# 教程中，你将使用 Visual Studio 创建和运行控制台应用程序，并在此过程中了解 [Visual Studio 集成开发环境 (IDE)](visual-studio-ide.md) 的部分功能。

如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)页免费安装。

## <a name="create-a-project"></a>创建项目

首先，创建 C# 应用程序项目。 项目类型随附了所需的全部模板文件，无需添加任何内容！

1. 打开 Visual Studio 2017。

2. 在顶部菜单栏，依次选择“文件” > “新建” > “项目”。

3. 在“新建项目”对话框的左窗格中，展开“C#”，然后选择“.NET Core”。 在中间窗格中，选择“控制台应用(.NET Core)”。 然后，将文件命名为“计算器”。

   ![Visual Studio IDE 中“新建项目”对话框中的控制台应用 (.NET Core) 项目模板](../ide/media/new-project-csharp-calculator-console-app.png)

### <a name="add-a-workgroup-optional"></a>添加工作组（可选）

如果未显示“控制台应用(.NET Core)”项目模板，可通过添加“.NET Core 跨平台开发”工作负载获取它。 可通过以下两种方式添加此工作负载，具体取决于计算机上安装的 Visual Studio 2017 更新。

#### <a name="option-1-use-the-new-project-dialog-box"></a>方式 1：打开“新建项目”对话框

1. 选择“新建项目”对话框左侧窗格中的“打开 Visual Studio 安装程序”链接。

   ![选择“新建项目”对话框中的“打开 Visual Studio 安装程序”链接](../ide/media/csharp-open-visual-studio-installer-generic-dark.png)

1. Visual Studio 安装程序启动。 选择“.NET Core 跨平台开发”工作负载，然后选择“修改”。

   ![Visual Studio 安装程序中的 .NET Core 跨平台开发工作负荷](../ide/media/dot-net-core-xplat-dev-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>方式 2：使用“工具”菜单栏

1. 取消“新建项目”对话框，再依次选择顶部菜单栏中的“工具” > “获取工具和功能”。

1. Visual Studio 安装程序启动。 选择“.NET Core 跨平台开发”工作负载，然后选择“修改”。

## <a name="create-a-c-console-calculator-app"></a>创建“C# 控制台计算器”应用程序

1. 打开 Visual Studio 2017，然后在顶部菜单栏中，选择“文件” > “新建” > “项目”。

1. 在“新建项目”对话框的左窗格中，展开“C#”，然后选择“.NET Core”。 在中间窗格中，选择“控制台应用(.NET Core)”。 然后，将文件命名为“计算器”。

1. 在代码编辑器中，输入或粘贴下面的代码：

    ```csharp
    using System;

    namespace Calculator
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Declare variables and then instantiate to zero
                double num1 = 0; double num2 = 0;

                // Display title as the C# console calculator app
                Console.WriteLine("Console Calculator in C#\r");
                Console.WriteLine("------------------------\n");

                // Ask the user to type the first number
                Console.WriteLine("Type a number, and then press Enter");
                num1 = Convert.ToDouble(Console.ReadLine());

                // Ask the user to type the second number
                Console.WriteLine("Type another number, and then press Enter");
                num2 = Convert.ToDouble(Console.ReadLine());

                // Ask the user to choose an option
                Console.WriteLine("Choose an option from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                // Use a switch statement to do the math
                switch (Console.ReadLine())
                {
                    case "a":
                        Console.WriteLine($"Your result: {num1} + {num2} = " + (num1 + num2));
                        break;
                    case "s":
                        Console.WriteLine($"Your result: {num1} - {num2} = " + (num1 - num2));
                        break;
                    case "m":
                        Console.WriteLine($"Your result: {num1} * {num2} = " + (num1 * num2));
                        break;
                    case "d":
                        // Ask the user to enter a non-zero divisor until they do so
                        while (num2 == 0)
                        {
                            Console.WriteLine("Enter a non-zero divisor: ");
                            num2 = Convert.ToDouble(Console.ReadLine());
                        }
                        Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                        break;
                    // Return text for an incorrect option entry
                    default:
                        Console.WriteLine("That is an incorrect option entry, please try again.");
                        break;
                }
                // Wait for the user to respond before closing
                Console.Write("Press any key to close the Calculator console app...");
                Console.ReadKey();
            }
        }
    }
    ```

   `static void Main(string[] args)` 后面的代码应如下面的屏幕截图所示：

   ![显示“C# 控制台计算器”应用程序的代码编辑器](../ide/media/csharp-console-calculator-code.png)

1. 选择“计算器”或按“F5”，以运行程序。

   ![选择工具栏中的“计算器”按钮以运行应用程序](../ide/media/csharp-console-calculator-button.png)

1. 在控制台窗口中查看你的应用。 按照提示操作后，应用程序应如下面的屏幕截图所示：

    ![显示“计算器”应用程序的控制台窗口，其中提示了要执行的操作。](../ide/media/csharp-console-calculator.png)

### <a name="close-the-app"></a>关闭应用程序

1. 按任意键，以关闭“计算器”应用程序。

1. 关闭 Visual Studio 中的输出窗格。

   ![关闭 Visual Studio 中的输出窗格](../ide/media/csharp-calculator-close-output-pane.png)

1. 关闭 Visual Studio。

## <a name="quick-answers-faq"></a>快速解答常见问题

下面是一个快速 FAQ，突出介绍了一些关键概念。

### <a name="what-is-c"></a>什么是 C#？

C# 是在 .NET Framework 和 .NET Core 上运行的类型安全编程语言。 使用 C#，可以创建 Windows 应用程序、客户端服务器应用程序、数据库应用程序、XML Web Service、分布式组件等。

### <a name="what-is-visual-studio"></a>什么是 Visual Studio？

Visual Studio 是适用于开发人员的生产力工具集成开发套件。 可将其视为可用于创建程序和应用程序的程序。

### <a name="what-is-a-console-app"></a>什么是控制台应用？

控制台应用获取输入，在命令行窗口（也称为 控制台）中显示输出。

### <a name="what-is-net-core"></a>.NET Core 是什么？

.NET Core 是 .NET Framework 的进一步演化。 .NET Framework 允许跨编程语言共享代码，而 .NET Core 增加了跨平台共享代码的功能。 此外，它还为开放源。

（.NET Framework 和 .NET Core 都包括预生成功能库。 它们还包括可用作运行代码的虚拟机的公共语言运行时 (CLR)。）

## <a name="next-steps"></a>后续步骤

恭喜你完成本教程！ 若要了解详情，请继续学习后续教程。

> [!div class="nextstepaction"]
> [C# 教程](/dotnet/csharp/tutorials/)

## <a name="see-also"></a>请参阅

* [面向零基础初学者的 C# 基础知识视频教程](https://mva.microsoft.com/en-us/training-courses/c-fundamentals-for-absolute-beginners-16169)
