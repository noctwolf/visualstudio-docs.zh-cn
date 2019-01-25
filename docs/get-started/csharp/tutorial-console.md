---
title: 教程：C# 控制台应用入门
description: 了解如何在 Visual Studio 中分步创建 C# 控制台应用程序。
ms.custom: seodec18, get-started
ms.date: 01/10/2019
ms.technology: vs-ide-general
ms.prod: visual-studio-dev15
ms.topic: tutorial
ms.devlang: CSharp
author: TerryGLee
ms.author: tglee
manager: douge
dev_langs:
- CSharp
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6114910f8c4cbeebc0301cc0c2167a49742823a5
ms.sourcegitcommit: 59c48e1e42b48ad25a4e198af670faa4d8dae370
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2019
ms.locfileid: "54204426"
---
# <a name="tutorial-get-started-with-a-c-console-app-in-visual-studio"></a>教程：Visual Studio 中的 C# 控制台应用入门

在本 C# 教程中，你将使用 Visual Studio 创建和运行控制台应用程序，并在此过程中了解 [Visual Studio 集成开发环境 (IDE)](../visual-studio-ide.md) 的部分功能。

如果尚未安装 Visual Studio，请转到 [Visual Studio 下载](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)页免费安装。

## <a name="create-a-project"></a>创建项目

创建 C# 应用程序项目。 项目类型随附了所需的全部模板文件，无需添加任何内容！

1. 打开 Visual Studio 2017。

2. 在顶部菜单栏，依次选择“文件” > “新建” > “项目”。

3. 在“新建项目”对话框的左窗格中，展开“C#”，然后选择“.NET Core”。 在中间窗格中，选择“控制台应用(.NET Core)”。 然后，将文件命名为“计算器”。

   ![Visual Studio IDE 中“新建项目”对话框中的控制台应用 (.NET Core) 项目模板](./media/new-project-csharp-calculator-console-app.png)

### <a name="add-a-workgroup-optional"></a>添加工作组（可选）

如果未显示“控制台应用(.NET Core)”项目模板，可通过添加“.NET Core 跨平台开发”工作负载获取它。 若要了解如何执行此操作，请参阅常见问题解答中的“[工作负荷是什么，以及如何添加工作负荷？](#workload)” 部分。

## <a name="create-the-app"></a>创建应用

首先，我们将添加代码，创建基础计算器。 然后，调整代码，添加功能。 之后，调试应用，查找并修复错误。 最后，优化代码，使其更高效。

让我们开始向项目中添加基础计算器代码。

1. 在代码编辑器中，删除默认“Hello World”代码。

    ![从新的计算器应用中删除默认 Hello World 代码](./media/csharp-console-calculator-deletehelloworld.png)

   具体来说，就是删除在代码编辑器中看到的所有代码。

1. 在代码编辑器中，输入或粘贴以下新的代码：

    ```csharp
    using System;

    namespace Calculator
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Declare variables and then initialize to zero
                int num1 = 0; int num2 = 0;

                // Display title as the C# console calculator app
                Console.WriteLine("Console Calculator in C#\r");
                Console.WriteLine("------------------------\n");

                // Ask the user to type the first number
                Console.WriteLine("Type a number, and then press Enter");
                num1 = Convert.ToInt32(Console.ReadLine());

                // Ask the user to type the second number
                Console.WriteLine("Type another number, and then press Enter");
                num2 = Convert.ToInt32(Console.ReadLine());

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
                        Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                        break;
                }
                // Wait for the user to respond before closing
                Console.Write("Press any key to close the Calculator console app...");
                Console.ReadKey();
            }
        }
    }
    ```
1. 选择“计算器”或按“F5”，以运行程序。

   ![选择工具栏中的“计算器”按钮以运行应用程序](./media/csharp-console-calculator-button.png)

   控制台窗口即会打开。

1. 在控制台窗口中，查看应用，然后按照提示添加数字 42 和 119。

   应用应如以下屏幕快照所示：

    ![显示“计算器”应用的控制台窗口，其中包括要执行的操作的相应提示](./media/csharp-console-calculator.png)

### <a name="add-decimals"></a>添加小数

计算器应用当前接受并返回整数。 但是，如果添加接受小数位的代码，会更精确。

如下面截图所示，如果运行应用，用数字 42 除以数字 119，结果为 0（零），这并不准确。

![“控制台”窗口显示“计算器”应用，该应用不返回带小数的数字](./media/csharp-console-calculator-nodecimal.png)

现在来修正代码，使其能够处理小数。

1. 按 Ctrl + F，以打开“查找和替换”控件。

1. 将 `int` 变量的每个实例更改为 `float`。

    ![展示如何将 int 变量更改为 float 的“查找和替换”控件动画](./media/find-replace-control-animation.gif)

1. 再次运行计算器应用，用数字 42 除以数字 119。

   注意，应用现在返回的是带小数的数字，而不是零。

    ![“控制台”窗口显示“计算器”应用，该应用现在返回一个带小数的数值](./media/csharp-console-calculator-decimal.png)

但是，应用现在只是能够生成带小数的结果。 让我们对代码做一些调整，以便应用可以计算小数。

1. 使用“查找和替换”控件 (Ctrl + F) 将 `float` 变量的每个实例都更改为 `double`，并将 `Convert.ToInt32` 方法的每个实例都更改为 `Convert.ToDouble`。

1. 运行计算器应用，用数字 42.5 除数字 119.75。

   注意，应用现在能够接受小数值，并返回具有更多小数位的数值。

    ![“控制台”窗口显示“计算器”应用，该应用现在接受小数，并返回具有更多小数位的数值](./media/csharp-console-calculator-usedecimals.png)

    （我们将在[修改代码](#revise-the-code)部分中固定小数位数。）

## <a name="debug-the-app"></a>调试应用

我们对基础计算器应用进行了改进，但它还不具备可应对异常（如用户输入错误）的故障保险机制。

例如，如果尝试用数字除以 0，或者在应用需要数字字符时输入 Alpha 字符（或者相反），应用将停止工作并返回错误。

现在来演练一些常见的用户输入错误，在[调试器](../../debugger/debugger-feature-tour.md)中查找并修复代码中的这些错误。

### <a name="fix-the-divide-by-zero-error"></a>修复“被零除”错误

如果尝试用数字除以 0，会导致控制台应用冻结。 然后 Visual Studio 会显示代码编辑器中的错误。

   ![Visual Studio 代码编辑器显示“被零除”错误](./media/csharp-console-calculator-dividebyzero-error.png)

现在更改代码以解决此错误。

1. 删除直接出现在 `case "d":` 和注释（内容为 `// Wait for the user to respond before closing`）之间的代码。

1. 将其替换为以下代码：

   ```csharp
            // Ask the user to enter a non-zero divisor until they do so
                while (num2 == 0)
                {
                    Console.WriteLine("Enter a non-zero divisor: ");
                    num2 = Convert.ToInt32(Console.ReadLine());
                }
                Console.WriteLine($"Your result: {num1} / {num2} = " + (num1 / num2));
                break;
        }
    ```

   添加代码后，带有 `switch` 语句的部分应如以下屏幕截图所示：

   ![Visual Studio 代码编辑器中修改后的“switch”部分](./media/csharp-console-calculator-switch-code.png)

现在，当用任何数字除以 0 时，应用会请求除以另一个数字。 更好的是：应用不会停止请求，直到提供非零数字。

   ![Visual Studio 代码编辑器显示“被零除”错误](./media/csharp-console-calculator-dividebyzero.png)

### <a name="fix-the-format-error"></a>修复“格式”错误

如果在应用需要数字字符时输入 Alpha 字符，控制台应用就会冻结，反之亦然。 然后 Visual Studio 会显示代码编辑器中的错误。

   ![Visual Studio 代码编辑器显示格式错误](./media/csharp-console-calculator-format-error.png)

若要修复这个错误，必须重构之前输入的代码。

#### <a name="revise-the-code"></a>修改代码

我们将应用分为两个类：`calculator` 和 `program`，而不是仅依赖于 `program` 类来处理所有代码。  

`calculator` 类处理大部分计算工作，`program` 类处理用户界面和错误捕获工作。

让我们开始吧。

1. 删除下列代码块*之后*的所有内容：

    ```csharp

    using System;

    namespace Calculator
    {

    ```

1. 接下来，添加新的 `calculator` 类，如下所示：

    ```csharp
    class Calculator
    {
        public static double DoOperation(double num1, double num2, string op)
        {
            double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error

            // Use a switch statement to do the math
            switch (op)
            {
                case "a":
                    result = num1 + num2;
                    break;
                case "s":
                    result = num1 - num2;
                    break;
                case "m":
                    result = num1 * num2;
                    break;
                case "d":
                    // Ask the user to enter a non-zero divisor
                    if (num2 != 0)
                    {
                        result = num1 / num2;
                    }
                    break;
                // Return text for an incorrect option entry
                default:
                    break;
            }
            return result;
        }
    }

    ```

1. 然后，添加新的 `program` 类，如下所示：

    ```csharp
    class Program
    {
        static void Main(string[] args)
        {
            bool endApp = false;
            // Display title as the C# console calculator app
            Console.WriteLine("Console Calculator in C#\r");
            Console.WriteLine("------------------------\n");

            while (!endApp)
            {
                // Declare variables and set to empty
                string numInput1 = "";
                string numInput2 = "";
                double result = 0;

                // Ask the user to type the first number
                Console.Write("Type a number, and then press Enter: ");
                numInput1 = Console.ReadLine();

                double cleanNum1 = 0;
                while (!double.TryParse(numInput1, out cleanNum1))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput1 = Console.ReadLine();
                }

                // Ask the user to type the second number
                Console.Write("Type another number, and then press Enter: ");
                numInput2 = Console.ReadLine();

                double cleanNum2 = 0;
                while (!double.TryParse(numInput2, out cleanNum2))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput2 = Console.ReadLine();
                }

                // Ask the user to choose an operator
                Console.WriteLine("Choose an operator from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                string op = Console.ReadLine();

                try
                {
                    result = Calculator.DoOperation(cleanNum1, cleanNum2, op);
                    if (double.IsNaN(result))
                    {
                        Console.WriteLine("This operation will result in a mathematical error.\n");
                    }
                    else Console.WriteLine("Your result: {0:0.##}\n", result);
                }
                catch (Exception e)
                {
                    Console.WriteLine("Oh no! An exception occurred trying to do the math.\n - Details: " + e.Message);
                }

                Console.WriteLine("------------------------\n");

                // Wait for the user to respond before closing
                Console.Write("Press 'n' and Enter to close the app, or press any other key and Enter to continue: ");
                if (Console.ReadLine() == "n") endApp = true;

                Console.WriteLine("\n"); // Friendly linespacing
            }
            return;
        }
    }
    ```
1. 选择“计算器”或按“F5”，以运行程序。

1. 按照提示，用数字 42 除以数字 119。 应用应如下图所示：

    ![“控制台”窗口显示重构后的“计算器”应用，其中包括要执行的操作的相应提示和针对错误输入的错误处理措施](./media/csharp-console-calculator-refactored.png)

    注意，在选择关闭控制台应用之前，可以选择输入更多等式。 而且，我们还减少了结果中小数位的位数。

## <a name="close-the-app"></a>关闭应用程序

1. 如果还没有这样做，请关闭计算器应用。

1. 关闭 Visual Studio 中的输出窗格。

   ![关闭 Visual Studio 中的输出窗格](./media/csharp-calculator-close-output-pane.png)

1. 在 Visual Studio 中，按 Ctrl+S 保存应用。

1. 关闭 Visual Studio。

## <a name="code-complete"></a>代码完成

在本次教程中，我们对计算器应用进行了许多更改。 应用现在可以更有效地处理计算资源，以及处理大多数的用户输入错误。

以下是完整代码，全部显示在同一个位置：

```csharp

using System;

namespace Calculator
{
    class Calculator
    {
        public static double DoOperation(double num1, double num2, string op)
        {
            double result = double.NaN; // Default value is "not-a-number" which we use if an operation, such as division, could result in an error

            // Use a switch statement to do the math
            switch (op)
            {
                case "a":
                    result = num1 + num2;
                    break;
                case "s":
                    result = num1 - num2;
                    break;
                case "m":
                    result = num1 * num2;
                    break;
                case "d":
                    // Ask the user to enter a non-zero divisor
                    if (num2 != 0)
                    {
                        result = num1 / num2;
                    }
                    break;
                // Return text for an incorrect option entry
                default:
                    break;
            }
            return result;
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            bool endApp = false;
            // Display title as the C# console calculator app
            Console.WriteLine("Console Calculator in C#\r");
            Console.WriteLine("------------------------\n");

            while (!endApp)
            {
                // Declare variables and set to empty
                string numInput1 = "";
                string numInput2 = "";
                double result = 0;

                // Ask the user to type the first number
                Console.Write("Type a number, and then press Enter: ");
                numInput1 = Console.ReadLine();

                double cleanNum1 = 0;
                while (!double.TryParse(numInput1, out cleanNum1))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput1 = Console.ReadLine();
                }

                // Ask the user to type the second number
                Console.Write("Type another number, and then press Enter: ");
                numInput2 = Console.ReadLine();

                double cleanNum2 = 0;
                while (!double.TryParse(numInput2, out cleanNum2))
                {
                    Console.Write("This is not valid input. Please enter an integer value: ");
                    numInput2 = Console.ReadLine();
                }

                // Ask the user to choose an operator
                Console.WriteLine("Choose an operator from the following list:");
                Console.WriteLine("\ta - Add");
                Console.WriteLine("\ts - Subtract");
                Console.WriteLine("\tm - Multiply");
                Console.WriteLine("\td - Divide");
                Console.Write("Your option? ");

                string op = Console.ReadLine();

                try
                {
                    result = Calculator.DoOperation(cleanNum1, cleanNum2, op);
                    if (double.IsNaN(result))
                    {
                        Console.WriteLine("This operation will result in a mathematical error.\n");
                    }
                    else Console.WriteLine("Your result: {0:0.##}\n", result);
                }
                catch (Exception e)
                {
                    Console.WriteLine("Oh no! An exception occurred trying to do the math.\n - Details: " + e.Message);
                }

                Console.WriteLine("------------------------\n");

                // Wait for the user to respond before closing
                Console.Write("Press 'n' and Enter to close the app, or press any other key and Enter to continue: ");
                if (Console.ReadLine() == "n") endApp = true;

                Console.WriteLine("\n"); // Friendly linespacing
            }
            return;
        }
    }
}

```

## <a name="quick-answers-faq"></a>快速解答常见问题

下面是一个快速 FAQ，突出介绍了一些关键概念。 常见问题解答还包括按教程中的步骤操作时可能出现的问题的解答。

### <a name="what-is-c"></a>什么是 C#？

C# 是在 .NET Framework 和 .NET Core 上运行的类型安全编程语言。 使用 C#，可以创建 Windows 应用程序、客户端服务器应用程序、数据库应用程序、XML Web Service、分布式组件等。

### <a name="what-is-visual-studio"></a>什么是 Visual Studio？

Visual Studio 是适用于开发人员的生产力工具集成开发套件。 可将其视为可用于创建程序和应用程序的程序。

### <a name="what-is-a-console-app"></a>什么是控制台应用？

控制台应用获取输入，在命令行窗口（也称为 控制台）中显示输出。

### <a name="what-is-net-core"></a>.NET Core 是什么？

.NET Core 是 .NET Framework 的进一步演化。 .NET Framework 允许跨编程语言共享代码，而 .NET Core 增加了跨平台共享代码的功能。 此外，它还为开放源。

（.NET Framework 和 .NET Core 都包括预生成功能库。 它们还包括可用作运行代码的虚拟机的公共语言运行时 (CLR)。）

### <a id="workload"></a>工作负荷是什么，以及如何添加工作负荷？

Visual Studio 中的工作负荷表示一组编程选项和模板，可以使用它们来自定义 Visual Studio 安装。 工作负荷只为所选编程语言和平台安装所需工具。 下面介绍如何安装。

#### <a name="option-1-use-the-new-project-dialog-box"></a>选项 1：使用“新建项目”对话框

1. 选择“新建项目”对话框左侧窗格中的“打开 Visual Studio 安装程序”链接。

   ![选择“新建项目”对话框中的“打开 Visual Studio 安装程序”链接](./media/csharp-open-visual-studio-installer-generic-dark.png)

1. Visual Studio 安装程序启动。 选择“.NET Core 跨平台开发”工作负载，然后选择“修改”。

   ![Visual Studio 安装程序中的 .NET Core 跨平台开发工作负荷](./media/dot-net-core-xplat-dev-workload.png)

#### <a name="option-2-use-the-tools-menu-bar"></a>选项 2：使用“工具”菜单栏

1. 取消“新建项目”对话框，再依次选择顶部菜单栏中的“工具” > “获取工具和功能”。

1. Visual Studio 安装程序启动。 选择“.NET Core 跨平台开发”工作负载，然后选择“修改”。

## <a name="next-steps"></a>后续步骤

恭喜你完成本教程！ 若要了解详情，请继续学习后续教程。

> [!div class="nextstepaction"]
> [C# 教程](/dotnet/csharp/tutorials/)

## <a name="see-also"></a>请参阅

* [面向零基础初学者的 C# 基础知识视频教程](https://mva.microsoft.com/en-us/training-courses/c-fundamentals-for-absolute-beginners-16169)