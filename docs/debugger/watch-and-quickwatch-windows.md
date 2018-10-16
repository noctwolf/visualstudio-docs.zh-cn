---
title: 在 Visual Studio 中的变量上设置监视 |Microsoft Docs
ms.custom: H1Hack27Feb2017
ms.date: 10/11/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.watch
helpviewer_keywords:
- debugging [Visual Studio], Watch window
- expressions [debugger], evaluating
- variables [debugger], evaluating
- expression evaluation
- registers, evaluating
- debugging [Visual Studio], expression evaluation
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ad08799c0dce3792e096291dfaf62d52e2515df4
ms.sourcegitcommit: 48bc8492973e93612e5afaba3b47d0f98aecf97c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2018
ms.locfileid: "49325011"
---
# <a name="set-a-watch-on-variables-using-the-watch-and-quickwatch-windows-in-visual-studio"></a>使用 Visual Studio 中的监视和快速监视窗口的变量上设置监视

当你进行调试时，可以使用**Watch**并**快速监视**监视变量和表达式。  区别是“监视”  窗口可以显示多个变量，而“快速监视”  窗口一次仅显示单个变量。

在调试会话期间，windows 才可用。 若要打开**Watch**窗口中，选择**调试** > **Windows** > **监视**，然后选择**观看 1**，**观看 2**，**观看 3**，或者**观看 4**。 若要打开**快速监视**窗口中，右键单击该变量，选择**快速监视**，或只需选择**调试** > **快速监视**.

## <a name="observe-variables-with-the-watch-window"></a>观察监视窗口使用的变量

具有多个变量，您可以观察**监视**窗口。 例如，如果你有以下代码：

```C++
int main()
{
    int a, b, c;
    a = 1;
    b = 2;
    c = 0;

    for (int i = 0; i < 10; i++)
    {
        a++;
        b *= 2;
        c = a + b;
    }

    return 0;
}

```

添加到三个变量的值**监视**窗口，如下所示：

1. 选择`c = a + b;`行。

2. 设置断点 (通过选择**调试** > **切换断点**或按 F9)。

3. 开始调试 (F5)。 执行在断点处停止。

4. 打开**Watch**窗口 (通过选择**调试** > **Windows** > **监视** >  **监视 1**，或按 Ctrl + Alt + W，1)。

5. 选择空的行，并键入变量`a`。 然后执行相同的操作变量`b`和`c`。

   ![监视变量](../debugger/media/watchvariables.png "WatchVariables")

6. 继续进行调试，推进调试器进度所需按 F11。

在循环访问 `for` 循环时，应该会看到变量值在改变。

如果您要在本机代码中进行编程，你有时可能需要限定变量名或具有变量名称的表达式的上下文。 上下文指变量所处的函数、源文件和模块。 如果需要限定上下文，可以使用上下文运算符语法。 有关详细信息，请参阅[上下文运算符 （c + +）](../debugger/context-operator-cpp.md)。

## <a name="observe-expressions-with-the-watch-window"></a>观察监视窗口使用的表达式

现在让我们尝试改为使用表达式。 你可以添加调试器所能识别的任何有效表达式。

例如，如果必须在上一部分中列出的代码，可以使用此表达式获取三个值的平均值：

![监视表达式](../debugger/media/watchexpression.png "WatchExpression")

在中计算表达式的规则**监视**窗口通常是与您的编码语言中表达式的计算规则相同。 如果你的表达式具有语法错误，预期会在代码编辑器中看到相同的编译器错误。 以下是一个示例：

![观看表达式错误](../debugger/media/watchexpressionerror.png "WatchExpressionError")

## <a name="bkmk_refreshWatch"></a> 刷新过期的监视值

中计算表达式时，可能会出现刷新图标 （环形箭头）**监视**窗口。 如果已关闭属性求值 (通过选择**工具** > **选项** > **调试** >  **常规**，然后清除**启用属性求值和其他隐式函数调用**)，并编写了以下代码：

```csharp
static void Main(string[] args)
{
    List<string> list = new List<string>();
    list.Add("hello");
    list.Add("goodbye");
}

```

如果应会看到类似于下图中的内容上设置监视`Count`列表的属性：

![RefreshWatch](../debugger/media/refreshwatch.png "RefreshWatch")

上图显示了错误或已过期的值。 通常可以通过选择图标来刷新值，但在某些情况下，可能会暂时不想刷新它。 首先，您需要知道为什么不计算值。

工具提示提供了有关为什么不计算表达式，如果你指向图标的信息。 如果显示旋转箭头，则不计算表达式出于以下原因之一：

- 在计算表达式时发生错误。 例如，计算可能超时或者变量可能超出范围。

- 表达式中有可能会触发应用程序中的副作用的函数调用 (请参阅[副作用和表达式](#bkmk_sideEffects)部分)。

- 已关闭自动求值的属性和隐式函数调用由调试器 (通过选择**工具** > **选项** > **调试** > **常规**，然后清除**启用属性求值和其他隐式函数调用**)。 无法自动计算表达式然后。

若要刷新值，选择刷新图标，或按空格键。 调试器尝试重新计算该表达式。 因为属性和其他隐式函数调用的自动求值已关闭，可能会出现刷新图标。 在这种情况下，调试器可以计算表达式的值。

可能会显示一个图标，即带类似于线程的两个波浪条纹的圆圈。 此图标表示调试器会计算该表达式，因为潜在的跨线程依赖关系。 换言之，计算代码需要暂时运行应用程序中的其他线程。 处于中断模式时，应用程序中的所有线程通常停止。 允许其他线程暂时运行可能会对程序状态产生意外影响，并会导致调试器忽略断点和在这些线程上引发的异常等事件。

## <a name="bkmk_sideEffects"></a> 副作用和表达式

计算某些表达式可以更改变量的值，或会影响程序的状态。 例如，计算下列表达式会更改 `var1`的值：

```csharp
var1 = var2
```

此代码可能会导致[副作用](https://en.wikipedia.org/wiki/Side_effect_\(computer_science\))。 通过改变程序运行的方式，副作用可使调试变得更加困难。

只有一次，当你首次输入计算已知具有副作用的表达式。 更多的计算将被禁用。 通过选择出现在值旁边的更新图标，可以手动重写此行为。

规避所有副作用的一种方法是关闭自动函数计算 (通过选择**工具** > **选项** > **调试** > **常规**，然后清除**启用属性求值和其他隐式函数调用**)。

当关闭属性计算或隐式函数调用时，可以使用 **ac** 格式修饰符（仅适用于 C#）强制计算。 请参阅[格式说明符在 C# 中的](../debugger/format-specifiers-in-csharp.md)。

## <a name="bkmk_objectIds"></a> 在监视窗口 （C# 和 Visual Basic） 中使用对象 Id

有时你想要观察特定对象的行为。 例如，你可能想要跟踪本地变量引用该变量超出范围后的对象。 可在 C# 和 Visual Basic 中，创建的特定实例的引用类型的对象 Id 和中使用它们**监视**窗口和断点条件中。 对象 ID 由公共语言运行时 (CLR) 调试服务生成并与该对象关联。

> [!NOTE]
> 对象 Id 创建弱引用，不会阻止对象被垃圾回收。 它们仅对当前调试会话有效。

在下面的代码中，一种方法创建`Person`使用本地变量，但你想要找出什么`Person`的名称是在另一种方法：

```csharp
class Person
{
    public Person(string name)
    {
        Name = name;
    }
    public string Name { get; set; }
}

public class Program
{
    static List<Person> _people = new List<Person>();
    public static void Main(string[] args)
    {
        MakePerson();
        DoSomething();
    }

    private static void MakePerson()
    {
        var p = new Person("Bob");
        _people.Add(p);
    }

    private static void DoSomething()
    {
        // more processing
         Console.WriteLine("done");
    }
}

```

你可以在“监视” `Person`**窗口中向该** 对象添加引用，如下所示：

1. 选择发生在创建对象的代码中的行。

2. 设置断点 (通过选择**调试** > **切换断点**或按 F9)。

3. 开始调试。

4. 当执行在断点处停止时，打开**局部变量**窗口 (通过选择**调试** > **Windows** > **局部变量**)，右键单击该变量，然后选择**创建对象 ID**。

   应会看到一个美元符号 (**$**) 在**局部变量**窗口中，这是对象 id。

   > [!NOTE]
   > 如果你想要查看对象的属性，如`Person.Name`，必须通过选择启用属性求值**工具** > **选项** >  **调试** > **常规**，然后设置**启用属性求值和其他隐式函数调用**。

5. 添加到的对象 ID **Watch**窗口中右击的美元符号和数字，然后选择**添加监视**。

6. 你想要观察的对象行为设置一个断点。  在前面的代码中，这个位置是在`DoSomething()`方法。

7. 继续调试。 当执行停止`DoSomething()`方法，**观看**窗口将显示`Person`对象。

## <a name="use-registers-in-the-watch-window-c-only"></a>在监视窗口 （c + +） 中使用寄存器

您可以添加寄存器名和使用的变量名 **$\<注册&nbsp;名称 >** 或 **@\<注册&nbsp;名称 >** 同时调试本机代码。 有关详细信息，请参阅 [Pseudovariables](../debugger/pseudovariables.md)。

## <a name="dynamic-view-and-the-watch-window"></a>动态视图和监视窗口

某些脚本语言 （例如，JavaScript 或 Python） 使用动态或[鸭子类型化](https://en.wikipedia.org/wiki/Duck_typing)，而.NET 语言 （在版本 4.0 以及更高版本） 支持对象难以观察使用一般调试窗口中，因为它们可能无法显示的运行时属性和方法。

**Watch**窗口可能会显示从实现的类型创建一个动态对象<xref:System.Dynamic.IDynamicMetaObjectProvider>接口。 显示此对象时，调试器将添加一个特殊**动态视图**如果您打开的对象名称的子节点**自动**窗口 (通过选择**调试** >  **Windows** > **自动**)。 此节点显示动态对象的动态成员，但不允许编辑成员值。

要插入新监视变量的对象强制转换为一个动态对象：

1. 右键单击的任何子**动态视图**。
2. 选择**添加监视**。 然后`object.name`变得`((dynamic) object).name`。

计算“动态视图”  的成员可能会有副作用。 有关副作用的说明，请参阅[副作用和表达式](#bkmk_sideEffects)部分。 对于 C#，调试器会自动不会重新计算中显示的值**动态视图**当进入新的代码行。 对于 Visual Basic，将自动刷新通过“动态视图”  添加的表达式。

有关如何刷新的说明**动态视图**值，请参阅[过期的刷新监视值](#bkmk_refreshWatch)部分。

如果你想要仅显示**动态视图**的对象，可以使用**动态**格式中的说明符**观看**窗口：

- C#：`ObjectName, dynamic`
- Visual Basic：`$dynamic, ObjectName`

“动态视图”  还可以提升 COM 对象的调试体验。 当在调试器进入 COM 对象包装在**System.__ComObject**，它将添加**动态视图**对象节点。

## <a name="observe-a-single-variable-or-expression-with-quickwatch"></a>观察单个变量或使用快速监视表达式

你可以使用“快速监视”  窗口观察单个变量。 例如，如果你有以下代码：

```csharp
static void Main(string[] args)
{
    int a, b;
    a = 1;
    b = 2;
    for (int i = 0; i < 10; i++)
    {
        a = a + b;
    }
}
```

您可以观察中的变量**快速监视**窗口，如下所示：

1. 在 `a = a + b;` 行上设置断点。

2. 开始调试。 执行在断点处停止。

3. 选择的变量`a`。

4. 选择**调试** > **快速监视**或按**Shift + F9**。 **快速监视**窗口会显示。 在中**值**框中，`a`变量显示具有值为 1。

   ![快速监视变量](../debugger/media/quickwatchvariable.png "QuickWatchVariable")

   若要评估表达式中使用变量，键入一个表达式类似于`a + b`到**表达式**框，然后单击**重新评估**。

   ![快速监视表达式](../debugger/media/quickwatchexpression.png "QuickWatchExpression")

   若要添加的变量或表达式**Watch**从窗口**快速监视**，选择**添加监视**。

   > [!NOTE]
   > **快速监视**窗口是一个模式对话框窗口中，因此无法继续调试，只要它已打开。

5. 关闭“快速监视”  窗口。 现在你可以继续进行调试，同时观察“监视” **窗口中向该** 窗口。

## <a name="see-also"></a>请参阅

[调试器窗口](../debugger/debugger-windows.md)
