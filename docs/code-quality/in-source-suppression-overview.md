---
title: 禁止显示 Visual Studio 中的代码分析警告
ms.date: 01/29/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- source suppression, code analysis
- code analysis, source suppression
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: aec11e54547f05e3ac7babae29e0c95737bc725e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31924413"
---
# <a name="suppress-code-analysis-warnings"></a>禁止显示代码分析警告

通常它可用于指示警告不适用。 这将指示已检查代码，并且可以禁止显示警告的团队成员。 在源抑制 (ISS) 使用<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性以禁止显示警告。 该属性可以被放置在靠近产生该警告的代码段。 你可以添加<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性到源文件，通过键入它，或者你可以使用的快捷菜单中的警告**错误列表**以将其自动添加。

<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性是条件的属性，它包括在您的托管的代码程序集的 IL 元数据，仅当在编译时定义 CODE_ANALYSIS 编译符号。

在 C + + /cli CLI，使用宏 CA\_禁止\_消息或 CA\_全局\_标头文件中的 SUPPRESS_MESSAGE 来添加特性。

> [!NOTE]
> 不应在发布版本使用在源代码中禁止显示以防止意外传送在源代码中禁止显示元数据。 此外，由于禁止显示源中的处理开销，可以降低你的应用程序的性能。

> [!NOTE]
> 如果将项目迁移到 Visual Studio 2017 时，您可能会突然会遇到这样相当多的代码分析警告。 如果你不准备好修复警告，并且想要暂时关闭代码分析，打开项目的属性页 (**项目** > ***项目*属性...**) 并转到**代码分析**选项卡。取消选择**生成时启用代码分析**，然后重新生成你的项目。 或者，你可以选择的不同，较小的规则集以针对代码运行。 请记住将重新打开当你准备好修复警告的代码分析。

## <a name="suppressmessage-attribute"></a>SuppressMessage 特性

当你选择**禁止**从代码分析警告中的上下文或右键单击菜单**错误列表**、<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性会被添加在代码中或项目的全局禁止显示文件。

<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性具有以下格式：

```vb
<Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")>
```

```csharp
[Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")]
```

```cpp
CA_SUPPRESS_MESSAGE("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")
```

该属性的属性包括：

- **规则类别**-定义了该规则的类别。 有关代码分析规则类别的详细信息，请参阅[托管代码警告](../code-quality/code-analysis-for-managed-code-warnings.md)。

- **规则 Id**的规则的标识符。 支持包括同时规则标识符的短期和长期名称。 短名称是 CAXXXX;全称是 CAXXXX:FriendlyTypeName。

- **两端对齐**-用于记录禁止显示消息的原因的文本。

- **消息 Id** -每条消息的问题的唯一标识符。

- **作用域**-在其取消该警告的目标。 如果未指定目标，则将它设置为目标的属性。 支持的作用域包括：

    - 模块

    - 命名空间

    - 资源

    - 类型

    - 成员

- **目标**-的标识符，用于以指定在其取消该警告的目标。 它必须包含完全限定的项名称。

## <a name="suppressmessage-usage"></a>SuppressMessage 使用情况

在向其级别取消代码分析警告<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>应用特性。 例如，可以在程序集、 模块、 类型、 成员或参数级别应用该属性。 这样做的目的是紧密耦合对代码的禁止显示信息发生了冲突。

禁止显示的一般形式包括规则类别和规则标识符，它包含可选的用户可读表示形式的规则名称。 例如：

`[SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]`

如果有尽量减少在源代码中禁止显示元数据的严格性能原因，则可以省略规则名称。 规则类别和其规则 ID 一起构成足够唯一的规则标识符。 例如：

`[SuppressMessage("Microsoft.Design", "CA1039")]`

出于可维护性原因，不建议省略规则名称。

## <a name="suppress-selective-violations-within-a-method-body"></a>禁止显示在方法体内的选择性冲突

禁止显示特性可以应用于方法，但不能嵌入在方法体中。 这意味着如果你添加禁止所有冲突的特定规则<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性设为该方法。

在某些情况下，你可能想要禁止显示该冲突，例如的特定实例，以便将来的代码不自动从代码分析规则中免除。 某些代码分析规则允许你执行此操作通过使用`MessageId`属性<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性。 一般情况下，旧的规则的冲突 （本地变量或参数） 的特定符号尊重`MessageId`属性。 [CA1500:VariableNamesShouldNotMatchFieldNames](../code-quality/ca1500-variable-names-should-not-match-field-names.md)是此类规则的示例。 但是，在可执行代码 （非符号） 上的冲突的旧规则不遵从`MessageId`属性。 此外，.NET Compiler Platform ("Roslyn") 分析器不遵从`MessageId`属性。

若要禁止显示特定的符号冲突的规则，指定的符号名称`MessageId`属性<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性。 下面的示例演示使用两个冲突的代码[CA1500:VariableNamesShouldNotMatchFieldNames](../code-quality/ca1500-variable-names-should-not-match-field-names.md)&mdash;另一个用于`name`变量，一个用于`age`变量。 仅违反`age`符号将被取消。

```vb
Public Class Animal
    Dim age As Integer
    Dim name As String

    <CodeAnalysis.SuppressMessage("Microsoft.Maintainability", "CA1500:VariableNamesShouldNotMatchFieldNames", MessageId:="age")>
    Sub PrintInfo()
        Dim age As Integer = 5
        Dim name As String = "Charlie"

        Console.WriteLine("Age {0}, Name {1}", age, name)
    End Sub

End Class
```

```csharp
public class Animal
{
    int age;
    string name;

    [System.Diagnostics.CodeAnalysis.SuppressMessage("Microsoft.Maintainability", "CA1500:VariableNamesShouldNotMatchFieldNames", MessageId = "age")]
    private void PrintInfo()
    {
        int age = 5;
        string name = "Charlie";

        Console.WriteLine($"Age {age}, Name {name}");
    }
}
```

## <a name="generated-code"></a>生成的代码

托管的代码编译器和某些第三方工具生成代码以加快代码的开发。 将出现在源文件中的编译器生成的代码通常将标有`GeneratedCodeAttribute`属性。

你可以选择是否要取消显示代码分析警告和错误生成的代码。 有关如何禁止显示此类警告和错误的信息，请参阅[如何： 禁止显示生成的代码的警告](../code-quality/how-to-suppress-code-analysis-warnings-for-generated-code.md)。

> [!NOTE]
> 代码分析将忽略`GeneratedCodeAttribute`当应用于整个程序集或单个参数。

## <a name="global-level-suppressions"></a>全局级禁止显示

托管的代码分析工具可检查是否`SuppressMessage`在程序集、 模块、 类型、 成员或参数级别应用的属性。 它还会引发对资源和命名空间冲突。 必须在全局级别应用这些冲突作用域和目标。 例如，以下消息禁止显示命名空间冲突：

`[module: SuppressMessage("Microsoft.Design", "CA1020:AvoidNamespacesWithFewTypes", Scope = "namespace", Target = "MyNamespace")]`

> [!NOTE]
> 禁止显示警告，其中包含命名空间范围内时，它禁止显示针对该命名空间本身的警告。 它不会取消对类型的命名空间中的警告。

可以通过指定一个显式的作用域表示任何抑制。 在全局级别必须位于这些禁止显示。 不能指定成员级别禁止显示的修饰类型。

全局级禁止显示是它们取消引用未映射到显式提供的用户源的编译器生成代码的消息的唯一方法。 例如，下面的代码将取消违反了针对编译器发出的构造函数：

`[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="Microsoft.Tools.FxCop.Type..ctor()")]`

> [!NOTE]
> `Target` 始终包含完全限定的项名称。

## <a name="global-suppression-file"></a>全局禁止显示文件

全局禁止显示文件维护全局级禁止显示或不指定目标的禁止显示。 例如，程序集级别冲突的禁止显示存储在此文件。 此外，某些 ASP.NET 禁止显示功能存储在此文件中，是因为项目级别设置不可用的窗体背后的代码。 全局禁止显示文件被创建并添加到你的项目选择的第一个时间**在项目禁止显示文件**选项**禁止**命令**错误列表**窗口。

## <a name="see-also"></a>请参阅

- <xref:System.Diagnostics.CodeAnalysis>
- [使用 Roslyn 分析器](../code-quality/use-roslyn-analyzers.md)