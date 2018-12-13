---
title: 检查变量的自动和局部变量窗口 |Microsoft Docs
ms.custom: seodec18
ms.date: 10/18/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.autos
- vs.debug.locals
helpviewer_keywords:
- debugger, variable windows
- debugging [Visual Studio], variable windows
ms.assetid: bb6291e1-596d-4af0-9f22-5fd713d6b84b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 584704471f9346611f240a3a24e0d45cf2eec364
ms.sourcegitcommit: 708f77071c73c95d212645b00fa943d45d35361b
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "53068349"
---
# <a name="inspect-variables-in-the-autos-and-locals-windows"></a>检查自动和局部变量窗口中的变量

**自动**并**局部变量**窗口进行调试时显示变量值。 在调试会话期间，windows 才可用。 **自动**窗口显示当前断点周围使用的变量。 **局部变量**窗口将显示在本地范围内，通常是当前函数或方法定义的变量。 如果这是你在尝试调试的代码的第一个时间，可能需要阅读[通过编写更好地修复 bugC#代码](../debugger/write-better-code-with-visual-studio.md)并[零基础调试](../debugger/debugging-absolute-beginners.md)之前开始阅读本文。

 **自动**窗口是适用于C#，Visual Basic、 c + + 和 Python 代码，而不是 JavaScript 或F#。
  
若要打开**自动**窗口中的，调试时，选择**调试** > **Windows** > **自动**，或按**Ctrl**+**Alt**+**V** > **A**。  

若要打开**局部变量**窗口中的，调试时，选择**调试** > **Windows** > **局部变量**，或按**Alt**+**4**。

> [!NOTE]
> 本主题适用于 Windows 上的 Visual Studio。 对于 Visual Studio for Mac ，请参阅[ Visual Studio for Mac 的数据可视化效果](/visualstudio/mac/data-visualizations)。

## <a name="use-the-autos-and-locals-windows"></a>使用自动和局部变量窗口

数组和对象中显示**自动**并**局部变量**windows 为树控件。 选择要展开的视图，以显示字段和属性的变量名称左侧的箭头。 下面是举例<xref:System.IO.FileStream?displayProperty=fullName>对象中**局部变量**窗口：

![局部变量 FileStream](../debugger/media/locals-filestream.png "局部变量 FileStream")

中的红色值**局部变量**或**自动**窗口意味着自上次评估以来已更改值。 此更改可能是从上一个调试会话，或因为您更改在窗口中的值。

在调试器窗口中的默认数字格式为 decimal。 若要将其更改为十六进制，右键单击**局部变量**或**自动**窗口，然后选择**十六进制显示**。 此更改会影响所有调试器窗口。

## <a name="edit-variable-values-in-the-autos-or-locals-window"></a>编辑自动或局部变量窗口中的变量值

若要编辑的值中的大多数变量**自动**或**局部变量**windows 中，双击值并输入新值。

你可以输入表达式作为一个值，例如 `a + b`。 调试器接受大多数合法的语言表达式。

在本机 C++ 代码中，你可能需要限定变量名的上下文。 有关详细信息，请参阅[上下文运算符（C++）](../debugger/context-operator-cpp.md)。

>[!CAUTION]
>在更改值和表达式之前，请确保你了解其后果。 一些可能存在的问题有：
>
>-   计算某些表达式可能会更改变量的值或以其他方式影响程序的状态。 例如，计算 `var1 = ++var2` 会更改 `var1` 和 `var2` 的值。 据说这些表达式具有[副作用](https://en.wikipedia.org/wiki/Side_effect_\(computer_science\))。 如果你不了解这些副作用，则可能会导致意外结果。
>
>-   编辑浮点值时，由于要将小数部分从十进制转换为二进制，因此所得的结果可能存在微小误差。 甚至看起来无关紧要的编辑都能引起浮点变量中的位的某些更改。

## <a name="change-the-context-for-the-autos-or-locals-window"></a>更改“自动”或“局部变量”窗口的上下文

可以使用**调试位置**工具栏来选择所需的函数、 线程或进程，这会更改为上下文**自动**并**局部变量**windows。

若要启用**调试位置**工具栏上，单击工具栏区域和选择的空白部分**调试位置**从下拉列表中或选择**视图** >  **工具栏** > **调试位置**。

设置断点并开始调试。 当到达断点时，执行暂停，你可以查看中的位置**调试位置**工具栏。

![调试位置工具栏](../debugger/media/debuglocationtoolbar.png "调试位置工具栏")

## <a name="bkmk_whatvariables"></a> 自动窗口中的变量 (C#，c + +、 Visual Basic 中，Python)

 不同的代码语言显示在不同的变量**自动**窗口。

 - 在 C# 和 Visual Basic 中，“自动”窗口显示当前或前一行中使用的任何变量。 例如，在C#或 Visual Basic 代码中，声明以下四个变量：

   ```csharp
       public static void Main()
       {
          int a, b, c, d;
          a = 1;
          b = 2;
          c = 3;
          d = 4;
       }
   ```

   在行上设置断点`c = 3;`，并启动调试器。 时暂停执行，**自动**窗口将显示：

   ![自动 CSharp](../debugger/media/autos-csharp.png "自动 CSharp")

   `c` 的值为 0，因为尚未执行 `c = 3` 行。

 - C + +**自动**窗口将显示执行会暂停当前行之前的至少三行中使用的变量。 例如，在 c + + 代码中，声明六个变量：

   ```C++
       void main() {
           int a, b, c, d, e, f;
           a = 1;
           b = 2;
           c = 3;
           d = 4;
           e = 5;
           f = 6;
       }
   ```

    在行上设置断点`e = 5;`并运行调试器。 当执行停止时，**自动**窗口将显示：

    ![自动 c + +](../debugger/media/autos-cplus.png "自动 c + +")

    未初始化变量 `e`，因为尚未执行 `e = 5` 行。

##  <a name="bkmk_returnValue"></a> View return values of method calls
 在.NET 和 c + + 代码中，可以检查中的返回值**自动**窗口时单步或跳出方法调用。 查看方法调用返回时它们不会存储在本地变量的值会很有用。 可以使用一种方法，作为一个参数，或另一种方法的返回值。

 例如，下面的 C# 代码将添加两个函数的返回值：

```csharp
static void Main(string[] args)
{
    int a, b, c, d;
    a = 1;
    b = 2;
    c = 3;
    d = 4;
    int x = sumVars(a, b) + subtractVars(c, d);
}

private static int sumVars(int i, int j)
{
    return i + j;
}

private static int subtractVars(int i, int j)
{
    return j - i;
}
```

要在“自动”窗口中查看 `sumVars()` 和 `subtractVars()` 方法调用的返回值，请执行以下操作：

1. 在 `int x = sumVars(a, b) + subtractVars(c, d);` 行上设置断点。  
   
1. 开始调试，并在断点处暂停执行，选择**单步跳过**或按**F10**。 您应看到在以下的返回值**自动**窗口：  
   
  ![自动返回值C# ](../debugger/media/autosreturnvaluecsharp2.png "自动返回值C#")  
  
## <a name="see-also"></a>请参阅  
 [什么是调试？](../debugger/what-is-debugging.md)  
 [通过编写更优质的 C# 代码来修复 bug](../debugger/write-better-code-with-visual-studio.md)  
 [首先看一下调试](../debugger/debugger-feature-tour.md)[调试器窗口](../debugger/debugger-windows.md)
