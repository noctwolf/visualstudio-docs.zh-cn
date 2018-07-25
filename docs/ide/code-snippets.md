---
title: 代码片段
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.ExpansionManagerImport
- vs.codesnippetmanager
helpviewer_keywords:
- surround with
- code snippets
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: 2d41a5a3995c9c93f17f090e5befc10a0bd544c3
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117207"
---
# <a name="code-snippets"></a>代码片段

代码片段是小块可重用的代码，可使用上下文菜单命令或热键组合将其插入代码文件中。 代码片段通常包含常用的代码块（如 `try-finally` 或 `if-else` 块），可用于插入整个类或方法。

代码片段可用于多种语言，例如 C#、C++、Visual Basic、XML 和 T-SQL。 要在安装项中查看对某语言可用的所有片段，请在 Visual Studio 的“工具”菜单中打开“代码片段管理器”，然后从顶部的下拉菜单中选择此语言。

![“代码片段管理器”对话框](media/code-snippets-manager.png)

可通过以下常见方法访问代码片段：

- 在菜单栏上，选择“编辑” > “IntelliSense” > “插入代码段”

- 在代码编辑器的右键单击或上下文菜单中，选择“代码段” > “插入代码段”

- 在键盘上按 Ctrl+K+X

## <a name="expansion-snippets-and-surround-with-snippets"></a>扩展式代码片段和外侧代码片段

Visual Studio 中有两种类型的代码片段：扩展代码片段和外侧代码片段，前者在指定的插入点添加，并且可以替换代码片段快捷方式，后者仅限 C# 和 C++，在所选代码块的周围添加。

扩展代码片段示例：在 C# 中，使用快捷方式 tryf 插入 try-finally 块：

```csharp
try
{

}
finally
{

}
```

可通过两种方式插入此代码片段：在代码窗口上下文菜单中依次单击“插入代码段”和“Visual C#”，键入 `tryf`，然后按 Tab。或者，可键入 `tryf`，再按 Tab 两次。

外侧代码片段的示例：在 C++ 快捷方式中，`if` 可用作插入代码片段，或者可用作外侧代码片段。 如果选择一行（例如 `return FALSE;`），然后单击“外侧代码” > “if”，即可让代码片段将围绕此行展开：

```cpp
if (true)
{
    return FALSE;
}
```

## <a name="snippet-replacement-parameters"></a>代码片段替换参数

代码片段可以包含替换参数，这些替换参数是占位符，必须对其进行替换以适应你编写的精确代码。 上例中的 `true` 是替换参数，你可以将其替换为适当的条件。 进行的替换将针对代码片段中同一个替换参数的每个实例重复。

例如，Visual Basic 中有一个用于插入属性的代码片段。 要插入代码片段，请在 Visual Basic 代码文件的右键单击或上下文菜单中选择“代码段” > “插入代码段”。 然后，选择“代码模式” > “属性、过程和事件” > “定义属性”。

![用于定义属性的代码片段菜单](media/code-snippets-vb-property.png)

插入以下代码：

```vb
Private newPropertyValue As String
Public Property NewProperty() As String
    Get
        Return newPropertyValue
    End Get
    Set(ByVal value As String)
        newPropertyValue = value
    End Set
End Property
```

如果将 `newPropertyValue` 更改为 `m_property`，则 `newPropertyValue` 的每个实例都会更改。 如果在属性声明中将 `String` 更改为 `Int`，则 Set 方法中的值也会更改为 `Int`。

## <a name="see-also"></a>请参阅

- [演练：创建代码片段](../ide/walkthrough-creating-a-code-snippet.md)
- [如何：分发代码片段](../ide/how-to-distribute-code-snippets.md)
- [有关使用代码片段的最佳做法](../ide/best-practices-for-using-code-snippets.md)
- [代码片段疑难解答](../ide/troubleshooting-snippets.md)
- [C# 代码片段](../ide/visual-csharp-code-snippets.md)
- [Visual C++ 代码片段](../ide/visual-cpp-code-snippets.md)
- [代码片段架构参考](../ide/code-snippets-schema-reference.md)