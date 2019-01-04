---
title: 禁止显示代码分析警告
ms.date: 08/03/2018
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: d72697a8969983d83445808b75c63bc8657ecf1f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53932863"
---
# <a name="suppress-code-analysis-warnings"></a>禁止显示代码分析警告

通常它可用于指示警告不适用。 这指示为团队成员已评审过代码，并且可以禁止显示警告。 源代码中禁止显示 (ISS) 使用<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性来禁止显示警告。 该属性可以被放置在靠近产生该警告的代码段。 您可以添加<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>中，键入属性的源文件也可以使用快捷菜单中的警告上**错误列表**以将其自动添加。

<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性是仅当在编译时定义 CODE_ANALYSIS 编译符号中的托管的代码程序集，IL 元数据包含条件属性。

在 C + + /cli CLI，使用宏 CA\_禁止\_消息或 CA\_GLOBAL\_SUPPRESS_MESSAGE 标头文件中的，若要将属性添加。

> [!NOTE]
> 不应使用在发布版本，在源代码中禁止显示来防止意外地传送在源代码中禁止显示元数据。 此外，由于在源代码中禁止显示的处理成本，可以降低您的应用程序的性能。

> [!NOTE]
> 如果将项目迁移到 Visual Studio 2017，可能会突然遇到大量代码分析警告。 这些警告的来源[Roslyn 分析器](roslyn-analyzers-overview.md)。 如果尚未准备好修复警告，则可以通过选择取消所有这些**分析** > **运行代码分析并取消未解决的问题**。
>
> ![运行代码分析并取消显示 Visual Studio 中的问题](media/suppress-active-issues.png)

## <a name="suppressmessage-attribute"></a>SuppressMessage 特性

当你选择**禁止**的上下文菜单或右键单击菜单中的代码分析警告**错误列表**、<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性添加到项目的全局禁止显示或者在你的代码文件。

<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性采用以下格式：

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

- **类别**-定义了该规则的类别。 有关代码分析规则类别的详细信息，请参阅[托管代码警告](../code-quality/code-analysis-for-managed-code-warnings.md)。

- **CheckId** -规则的标识符。 支持包括以上两个规则标识符的短期和长期名称。 短名称是 CAXXXX;长名称是 CAXXXX:FriendlyTypeName。

- **理由**-用于记录取消消息的规则的原因的文本。

- **MessageId** -为每个消息问题的唯一标识符。

- **作用域**-取消该警告的目标。 如果未指定目标，则将它设置为属性的目标。 受支持的作用域包括：

    - 模块

    - 命名空间

    - 资源

    - 类型

    - 成员

- **目标**-用于取消该警告将目标指定的标识符。 它必须包含完全限定的项的名称。

## <a name="suppressmessage-usage"></a>SuppressMessage 使用情况

在向其级别禁止显示代码分析警告<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>应用属性。 例如，可以在程序集、 模块、 类型、 成员或参数级别应用该属性。 这样做的目的是紧密耦合到代码的禁止显示信息发生冲突。

禁止显示的一般形式包括规则类别和规则标识符，其中包含的规则名称的可选用户可读表示形式。 例如：

`[SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]`

如果有严格的性能的最大程度减少在源代码中禁止显示元数据的原因，可以省略规则名称。 规则类别和其规则 ID 一起构成足够唯一的规则标识符。 例如：

`[SuppressMessage("Microsoft.Design", "CA1039")]`

出于可维护性考虑，不建议省略规则名称。

## <a name="suppress-selective-violations-within-a-method-body"></a>禁止显示方法体中的选择性冲突

禁止显示特性可以应用于方法，但不能在方法体中嵌入。 这意味着，如果添加禁止所有冲突的特定规则<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性为该方法。

在某些情况下，你可能想要禁止显示此违反行为，例如特定实例，使未来的代码不是自动代码分析规则中免除。 某些代码分析规则，可使用执行此操作`MessageId`属性的<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性。 一般情况下，旧规则的冲突 （本地变量或参数） 的特定符号方面`MessageId`属性。 [CA1500:VariableNamesShouldNotMatchFieldNames](../code-quality/ca1500-variable-names-should-not-match-field-names.md)举例说明此类规则。 但是，可执行代码 （非符号） 上是否存在冲突的旧规则不遵从`MessageId`属性。 此外，.NET 编译器平台 ("Roslyn") 分析器不遵从`MessageId`属性。

若要禁止显示特定符号违反规则，请指定的符号名称`MessageId`属性的<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute>属性。 下面的示例演示具有两个冲突的代码[CA1500:VariableNamesShouldNotMatchFieldNames](../code-quality/ca1500-variable-names-should-not-match-field-names.md)&mdash;另一个用于`name`变量，一个用于`age`变量。 仅对于冲突`age`禁止显示符号。

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

托管的代码编译器和一些第三方工具生成代码以加快代码的开发。 在源文件中出现的编译器生成的代码通常标有`GeneratedCodeAttribute`属性。

您可以选择是否要取消显示代码分析警告和错误生成的代码。 有关如何禁止显示此类警告和错误的信息，请参阅[如何：禁止显示生成的代码的警告](../code-quality/how-to-suppress-code-analysis-warnings-for-generated-code.md)。

> [!NOTE]
> 代码分析忽略了`GeneratedCodeAttribute`时应用于整个程序集或单个参数。

## <a name="global-level-suppressions"></a>全局级禁止显示

托管的代码分析工具可检查`SuppressMessage`应用于程序集、 模块、 类型、 成员或参数级别的属性。 它还会激发针对资源和命名空间冲突。 必须在全局级别应用这些冲突作用域和有针对性。 例如，以下消息禁止显示命名空间冲突：

`[module: SuppressMessage("Microsoft.Design", "CA1020:AvoidNamespacesWithFewTypes", Scope = "namespace", Target = "MyNamespace")]`

> [!NOTE]
> 禁止显示警告，其中包含命名空间范围内时，它将阻止对自身的命名空间的警告。 它不会取消该警告针对在命名空间内的类型。

可以通过指定显式作用域表示任何禁止显示。 在全局级别还必须遵循这些禁止显示。 不能通过修饰类型来指定成员级禁止显示。

全局级禁止显示是唯一的方法来禁止显示编译器生成的代码未映射到显式提供的用户源是指的消息。 例如，以下代码取消针对编译器发出的构造函数冲突：

`[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="Microsoft.Tools.FxCop.Type..ctor()")]`

> [!NOTE]
> `Target` 始终包含完全限定的项名称。

## <a name="global-suppression-file"></a>全局禁止显示文件

全局禁止显示文件维护全局级禁止显示或不指定目标的禁止显示的禁止显示。 例如，禁止显示程序集级别存在冲突存储在该文件中。 此外，某些 ASP.NET 禁止显示存储在此文件中，是因为项目级设置不可用于窗体背后的代码。 创建全局禁止显示文件并将其添加到项目中选择第一次**在项目禁止显示文件**的选项**禁止**命令**错误列表**窗口。

## <a name="see-also"></a>请参阅

- <xref:System.Diagnostics.CodeAnalysis>
- [使用 Roslyn 分析器](../code-quality/use-roslyn-analyzers.md)