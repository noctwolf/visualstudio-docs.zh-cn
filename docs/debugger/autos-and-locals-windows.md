---
title: 检查自动和局部变量窗口中的变量 |Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 04/17/2018
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
ms.openlocfilehash: b196d993e7091fd9d4b09fe3c228346e7421911e
ms.sourcegitcommit: a7de99f36e9ead7ea9e9bac23c88d05ddfc38b00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2018
ms.locfileid: "52257207"
---
# <a name="inspect-variables-in-the-autos-and-locals-windows"></a>检查自动和局部变量窗口中的变量

在调试时，**自动**和**局部变量**窗口会显示变量值。 这些窗口仅在调试会话期间可用。 **自动**窗口显示在当前断点附近的变量。 **局部变量**窗口显示在局部范围内定义的变量，通常是当前函数或方法。 如果这是您第一次尝试调试代码，那么在阅读本文之前，您可能需要阅读[编写更好地C#使用 Visual Studio 代码](../debugger/write-better-code-with-visual-studio.md)和[零基础调试](../debugger/debugging-absolute-beginners.md)。

 **自动**窗口可用于C#，Visual Basic，C ++和Python代码，但不适用于 JavaScript 或F#。
 
要在调试时打开**自动**窗口，请选择**Debug> Windows> Autos**，或按**Ctrl + Alt + V> A**.

要在调试时打开**局部变量**窗口，请选择**Debug> Windows> Locals**，或按**Alt + 4**。

如果您需要了解基本调试的详细信息，请参阅[开始使用调试器](../debugger/getting-started-with-the-debugger.md)。

> [!NOTE]
> 本主题适用于 Windows 上的 Visual Studio。 对于 Visual Studio for Mac ，请参阅[ Visual Studio for Mac 的数据可视化效果](/visualstudio/mac/data-visualizations)。

## <a name="use-the-autos-and-locals-windows"></a>使用自动和局部变量窗口

数组和对象在**自动**和**局部变量**窗口中显示为树形控件。 选择变量名称左侧的箭头以展开视图以显示字段和属性。 以下是**局部变量**窗口中<xref:System.IO.FileStream?displayProperty=fullName>对象的示例：

![局部变量 FileStream](../debugger/media/locals-filestream.png "局部变量 FileStream")

**局部变量**或**自动**窗口中的红色值表示自上次评估后值已更改。 更改可能来自之前的调试会话，也可能是因为您更改了窗口中的值。

调试器窗口中的默认数字格式为十进制。 要将其更改为十六进制，请在**局部变量**或**自动**窗口中单击鼠标右键，然后选择**十六进制显示**。 此更改会影响所有调试器窗口。


## <a name="edit-variable-values-in-the-autos-or-locals-window"></a>编辑自动或局部变量窗口中的变量值

要在**自动**或**局部变量**窗口中编辑大多数变量的值，请双击该值并输入新值。

你可以输入表达式作为一个值，例如 `a + b`。 调试器接受大多数合法的语言表达式。

在本机 C++ 代码中，你可能需要限定变量名的上下文。 有关详细信息，请参阅[上下文运算符 （c + +）](../debugger/context-operator-cpp.md)。


>[!CAUTION]
>在更改值和表达式之前，请确保您了解其后果。 一些可能的问题是：
>
>-   计算某些表达式可能会更改变量的值或以其他方式影响程序的状态。 例如，计算`var1 = ++var2`会更改`var1`和`var2`的值。 这些表达式被视为具有[副作用](https://en.wikipedia.org/wiki/Side_effect_\(computer_science\))。 如果您不了解副作用，可能会导致意外结果。
>
>-   编辑浮点值时，由于要将小数部分从十进制转换为二进制，因此所得的结果可能存在微小误差。 甚至看起来无关紧要的编辑都能引起浮点变量中的位的某些更改。

## <a name="change-the-context-for-the-autos-or-locals-window"></a>更改自动或局部变量窗口的上下文

您可以使用**调试位置**工具栏选择所需的函数、 线程或进程，从而更改**自动**和**局部变量**窗口的上下文。

要启用**调试位置**工具栏，请单击工具栏区域的空白部分，然后从下拉列表中选择**调试位置**，或选择**视图** >  **工具栏** > **调试位置**。

设置断点并开始调试。 当命中断点时，执行暂停，您可以在**调试位置**工具栏中看到该位置。

![调试位置工具栏](../debugger/media/debuglocationtoolbar.png "调试位置工具栏")

## <a name="bkmk_whatvariables"></a> 自动窗口中的变量 (C#，c + +、 Visual Basic ，Python)

 不同的代码语言在**自动**窗口中显示不同的变量。

 - 在C#和 Visual Basic中，**自动**窗口显示当前行或上一行使用的任何变量。 例如，在C#或Visual Basic代码中，声明以下四个变量：

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

   在`c = 3;`行上设置断点，然后启动调试器。 执行暂停时，**自动**窗口将显示：

   ![自动 CSharp](../debugger/media/autos-csharp.png "自动 CSharp")

   `c`的值为 0，因为`c = 3`尚未执行。

 - 在C ++中，**自动**窗口显示在暂停执行的当前行之前至少三行中使用的变量。 例如，在C ++代码中，声明六个变量：

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

    在`e = 5;`这行设置断点并运行调试器。 当执行停止时，**自动**窗口将显示：

    ![自动 c + +](../debugger/media/autos-cplus.png "自动 c + +")

    变量`e`未初始化，因为`e = 5`尚未执行。

##  <a name="bkmk_returnValue"></a> 查看方法调用的返回值
 在.NET 和 C ++ 代码中，当您单步调试或退出方法调用时，可以在**自动**窗口中检查返回值。 当没有保存在局部变量中时，查看方法调用返回值会非常有用。 方法可以用作参数，也可以用作另一种方法的返回值。

例如，以下C＃代码添加了两个函数的返回值：


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

要在**自动**窗口中查看`sumVars()`和`subtractVars()`方法调用的返回值，请执行以下操作：

1. 在 `int x = sumVars(a, b) + subtractVars(c, d);` 行上设置断点。  
   
1. 开始调试，当执行在断点处暂停时，选择**单步跳过**或按**F10**。 您应该在**自动**窗口中看到以下返回值： 
   
  ![自动返回值C# ](../debugger/media/autosreturnvaluecsharp2.png "自动返回值C#")  
  
## <a name="see-also"></a>请参阅  
 [什么调试？](../debugger/what-is-debugging.md)  
 [更好地编写C#使用 Visual Studio 代码](../debugger/write-better-code-with-visual-studio.md)  
 [首先看一下调试](../debugger/debugger-feature-tour.md)[调试器窗口](../debugger/debugger-windows.md)
