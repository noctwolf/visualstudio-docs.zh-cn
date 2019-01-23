---
title: 检查变量的自动和局部变量窗口 |Microsoft Docs
ms.custom: seodec18
ms.date: 10/18/2018
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
ms.openlocfilehash: f84b18cd3d4bfbae949ba4dd3199bace6604148f
ms.sourcegitcommit: 59c48e1e42b48ad25a4e198af670faa4d8dae370
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2019
ms.locfileid: "54204478"
---
# <a name="inspect-variables-in-the-autos-and-locals-windows"></a>检查自动和局部变量窗口中的变量

在调试时，“自动变量”和“局部变量”窗口会显示变量值。 仅在调试会话期间，这两个窗口才可用。 “自动变量”窗口显示当前断点周围使用的变量。 “局部变量”窗口显示在局部范围内定义的变量，通常是当前函数或方法。 如果是首次尝试调试代码，那么在阅读本文前，可能需要阅读[面向初学者的调试](../debugger/debugging-absolute-beginners.md)和[通过编写更好的 C# 代码来修复 bug](../debugger/write-better-code-with-visual-studio.md)。

 “自动变量”窗口可用于 C#、Visual Basic、C++ 和 Python 代码，但不可用于 JavaScript 或 F#  。
  
若要打开“自动变量”窗口，请在调试时依次选择“调试” > “窗口” > “自动变量”，或按 Ctrl+Alt+V  >  A 调试。  

若要打开“局部变量”窗口，请在调试时选择“调试” > “窗口” > “局部变量”，或按 Alt+4。

> [!NOTE]
> 本主题适用于 Visual Studio  Windows 版。 对于 Visual Studio for Mac，请参阅 [Visual Studio for Mac 的数据可视化效果](/visualstudio/mac/data-visualizations)。

## <a name="use-the-autos-and-locals-windows"></a>使用自动和局部变量窗口

数组和对象在“自动变量”和“局部变量”窗口中显示为树形控件。 选择变量名称左侧的箭头可展开视图，以显示字段和属性。 以下是“局部变量”窗口中 <xref:System.IO.FileStream?displayProperty=fullName> 对象的示例：

![Locals-FileStream](../debugger/media/locals-filestream.png "Locals-FileStream")

“局部变量”或“自动变量”窗口中的红色值表示自上次评估后值已更改。 此更改可能是在上一个调试会话中进行的，也可能是在窗口中更改了值。

调试器窗口中的默认数字格式为十进制。 若要将其更改为十六进制，请在“局部变量”或“自动”窗口中右键单击，然后选择“十六进制显示”。 此更改会影响所有调试器窗口。

## <a name="edit-variable-values-in-the-autos-or-locals-window"></a>编辑自动或局部变量窗口中的变量值

若要编辑“自动”或“局部变量”窗口中大多数变量的值，请双击该值并输入新值。

你可以输入表达式作为一个值，例如 `a + b`。 调试器接受大多数合法的语言表达式。

在本机 C++ 代码中，你可能需要限定变量名的上下文。 有关详细信息，请参阅[上下文运算符（C++）](../debugger/context-operator-cpp.md)。

>[!CAUTION]
>在更改值和表达式之前，请确保你了解其后果。 一些可能存在的问题有：
>
>-   计算某些表达式可能会更改变量的值或以其他方式影响程序的状态。 例如，计算 `var1 = ++var2` 会更改 `var1` 和 `var2` 的值。 据说这些表达式具有[副作用](https://en.wikipedia.org/wiki/Side_effect_\(computer_science\))。 如果你不了解这些副作用，则可能会导致意外结果。
>
>-   编辑浮点值时，由于要将小数部分从十进制转换为二进制，因此所得的结果可能存在微小误差。 甚至看起来无关紧要的编辑都能引起浮点变量中的位的某些更改。

## <a name="change-the-context-for-the-autos-or-locals-window"></a>更改“自动”或“局部变量”窗口的上下文

可使用“调试位置”工具栏选择所需的函数、线程或进程，这将更改“自动”和“局部变量”窗口的上下文。

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

   ![Autos-CSharp](../debugger/media/autos-csharp.png "Autos-CSharp")

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

    ![Autos-C++](../debugger/media/autos-cplus.png "Autos-C++")

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
