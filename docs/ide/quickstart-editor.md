---
title: "Visual Studio 中的编辑功能简介 | Microsoft Docs"
ms.custom: 
ms.date: 11/30/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 2bbdabf7d35c2705d028c84ddc6c6dc82f71ff48
ms.sourcegitcommit: 342e5ec5cec4d07864d65379c2add5cec247f3d6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="quickstart-use-the-code-editor"></a>快速入门：使用代码编辑器

在这个 10 分钟的编辑器简介中，我们会向文件添加代码，了解 Visual Studio 编写、导航和了解代码的简便方法。

此快速入门假定你已熟悉编程语言。 如果不熟悉，则建议首先查看其中一个编程快速入门，如使用 [Python](../ide/quickstart-python.md) 或 [C#](../ide/tutorial-csharp-aspnet-core.md) 创建 Web 应用，或使用 [Visual Basic](../ide/quickstart-visual-basic-console.md) 或 [C++](../ide/quickstart-cpp.md) 创建控制台应用。

## <a name="create-a-new-code-file"></a>创建新代码文件

先创建一个新文件并向其添加一些代码。 请注意，我们不需要创建项目来使用编辑器提供的便利。

1. 打开 Visual Studio，在菜单栏上的“文件”菜单中，选择“新建” > “文件...”。

1. 在“新建文件”对话框的“常规”类别中，选择“Visual C# 类”，然后选择“打开”。

   编辑器中将打开主干为 C# 类的新文件。

## <a name="using-code-snippets"></a>使用代码片段

Visual Studio 提供了实用的代码片段，可快速方便地生成常用代码块。 [代码片段](../ide/code-snippets.md)可用于不同编程语言，包括 C#、Visual Basic 和 C++。 我们将 C# `void Main` 代码片段添加到文件。

1. 将光标置于 `Class1` 构造函数的右大括号下方，然后输入字符 `svm`。

   此时会看到一个 IntelliSense 对话框，其中包含有关 `svm` 代码片段的信息。

   ![IntelliSense 代码片段](media/quickstart-intellisense-snippet.png)

1. 按 Tab 两次，插入代码片段。

   你会看到 `static void Main()` 方法签名被添加到文件。 `Main()` 方法是 C# 应用程序的入口点。

对于不同语言，可用代码片段不同。 依次选择“编辑”、“IntelliSense”、“插入代码片段...”，然后选择语言的文件夹，即可查看编程语言的可用代码片段。 对于 C#，该列表如下所示：

![C# 代码片段列表](media/quickstart-code-snippet-list.png)

该列表包含用于创建类、构造函数、`Console.WriteLine()`、`for` 循环、`if` 和 `switch` 语句等的代码片段。

## <a name="commenting-out-code"></a>为代码添加注释

工具栏提供了许多按钮，可提高编码效率。 例如，你可切换到 IntelliSense 完成模式、增加或减少缩进、设置书签或为代码添加注释。 本节将介绍如何为不想编译的代码添加注释。

![编辑器工具栏](media/quickstart-editor-toolbar.png)

1. 将以下代码粘贴到 `Main()` 方法主体中。

    ```csharp
    // _words is a string array that we'll sort alphabetically
    string[] _words = {
        "the",
        "quick",
        "brown",
        "fox",
        "jumps"
    };

    string[] morewords = {
        "over",
        "the",
        "lazy",
        "dog"
    };

    IEnumerable<string> query = from word in _words
                                orderby word.Length
                                select word;
    ```

1. 我们现在没有使用 `morewords` 变量，但稍后可能会用到，所以我们不想删除它。 那我们就来为这些行加上注释。 选择整个 `morewords` 定义直到结束分号，然后选择工具栏上的“为选定行添加注释”，或按 Ctrl+K，Ctrl+C。

   ![“添加注释”按钮](media/quickstart-comment-out.png)

   C# 注释字符 `//` 添加到了每个所选行的开始处，从而为代码添加注释。

## <a name="collapsing-code-blocks"></a>折叠代码块

我们不想看到生成的 `Class1` 的空构造函数，所以为了让代码更整洁，我们将其折叠。 在构造函数第一行的边距中选择内部带有减号的小灰色框。 如果你使用的是键盘，也可将光标置于构造函数代码中的任意位置，然后按 Ctrl+M，Ctrl+M。

![“大纲显示折叠”按钮](media/quickstart-collapse.png)

代码块折叠到第一行，后跟省略号 (`...`)。 若要再次展开代码块，请单击现在带有加号的相同灰色框，或者再次按 Ctrl+M，Ctrl+M。 此功能被称为[大纲显示](../ide/outlining.md)，在折叠长方法或整个类时特别有用。

## <a name="viewing-symbol-definitions"></a>查看符号定义

通过 Visual Studio 编辑器可轻松查看类型、方法等的定义。一种方法是导航到包含定义的文件，例如通过选择“转到定义”，转到引用符号的任何位置。 使用“[速览定义](../ide/go-to-and-peek-definition.md#peek-definition)”速度更快，不会干扰你处理文件。 我们来快速查看一下 `string` 的定义。

1. 右键单击出现的任意 `string`，然后选择内容菜单上的“速览定义”，或者按 Alt+F12。

   此时会出现一个弹出窗口，其中包含 `String` 类的定义。 可在弹出窗口中滚动，甚至还可从速览的代码中查看另一类型的定义。

   ![“速览定义”窗口](media/quickstart-peek-definition.png)

1. 选择弹出窗口右上方的“x”小框，关闭“速览定义”窗口。

## <a name="using-intellisense-to-complete-words"></a>使用 IntelliSense 完成单词

编写代码时，[IntelliSense](../ide/using-intellisense.md) 是非常宝贵的资源。 它可显示某个类型的可用成员信息，或某个方法不同重载的参数详情。 还可用于完成单词，从而在输入大量字符后消除字符带来的歧义。 我们来添加一行代码，将有序字符串打印到控制台窗口。

1. 在 `query` 变量下，开始键入以下代码：

   ```csharp
   foreach (string str in qu
   ```

   IntelliSense 会显示有关 `query` 符号的“快速信息”。

   ![IntelliSense 单词完成](media/quickstart-intellisense-completion-list.png)

1. 若要通过 IntelliSense 的“完成单词”功能插入 `query` 的剩余部分，请按 Tab。

1. 完成后，代码块如以下代码所示。 你甚至可以通过输入 `cw`，然后按 Tab 两次来生成 `Console.WriteLine` 代码，再次练习使用代码片段。

   ```csharp
   foreach (string str in query)
   {
      Console.WriteLine(str);
   }
   ```

## <a name="refactoring-a-name"></a>重构名称

没有谁能一次就得到正确的代码，代码中可能要更改的一项内容是变量或方法的名称。 我们来试试 Visual Studio 的[重构](../ide/refactoring-in-visual-studio.md)功能，将 `_words` 变量重命名为 `words`。

1. 将光标置于 `words` 变量的定义上，然后从右键菜单或上下文菜单选择“重命名...”，或按 Ctrl+R，Ctrl+R。

   此时编辑器右上角会弹出一个“重命名”对话框。

1. 输入所需名称 `words`。 请注意，查询中对 `words` 的引用也会自动重命名。 在按 Enter 前，请在“重命名”弹出框中选中“包含注释”复选框。

   ![“重命名”对话框](media/quickstart-rename.png)

1. 按 **Enter**。

   出现的两处 `words` 均被重命名，代码注释中对 `words` 的引用也被重命名。

## <a name="next-steps"></a>后续步骤

你已经完成了 Visual Studio 编辑器的快速入门！ 接下来，你可以尝试了解 Visual Studio IDE 的一些其他快速入门，查看[导航代码](../ide/navigating-code.md)的更多方法，或查看链接，详细了解我们介绍的功能。 总之，祝你编码愉快！

## <a name="see-also"></a>请参阅

- [快速入门：初步了解 Visual Studio IDE](../ide/quickstart-ide-orientation.md)
- [快速入门：个性化设置 Visual Studio IDE 和编辑器](../ide/quickstart-personalize-the-ide.md)
- [快速入门：项目和解决方案](../ide/quickstart-projects-solutions.md)
- [代码片段](../ide/code-snippets.md)
- [大纲显示](../ide/outlining.md)
- [转到定义和速览定义](../ide/go-to-and-peek-definition.md)
- [重构](../ide/refactoring-in-visual-studio.md)
- [使用 IntelliSense](../ide/using-intellisense.md)