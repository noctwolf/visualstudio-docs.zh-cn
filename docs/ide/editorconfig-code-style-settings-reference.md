---
title: EditorConfig 的 .NET 编码约定设置
ms.date: 06/14/2018
ms.topic: reference
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- coding conventions [EditorConfig]
- EditorConfig coding conventions
- language code style rules [EditorConfig]
- formatting conventions [EditorConfig]
author: kuhlenh
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3cdd9f0b46c578f713b7f2af2940f4d7742df19a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62557211"
---
# <a name="net-coding-convention-settings-for-editorconfig"></a>EditorConfig 的 .NET 编码约定设置

通过使用 [EditorConfig](../ide/create-portable-custom-editor-options.md) 文件，可在基本代码中定义和维护一致的代码样式。 EditorConfig 包括多个核心格式设置属性，如 `indent_style` 和 `indent_size`。 在 Visual Studio 中，还可使用 EditorConfig 文件配置 .NET 编码约定设置。 可以启用或禁用单个 .NET 编码约定，并可通过严重级别配置强制实施每个规则的程度。

> [!TIP]
> - 在 .editorconfig 文件中定义编码约定时，可配置内置到 Visual Studio 中的[代码样式分析器](../code-quality/roslyn-analyzers-overview.md)如何分析你的代码。 .editorconfig 文件是适用于这些分析器的配置文件。
> - Visual Studio 的代码样式首选项还可以在[文本编辑器选项](code-styles-and-quick-actions.md)对话框中进行设置。 但是，.editorconfig 设置优先使用，在“选项”中设置的首选项不与特定项目相关联。

本文的末尾包含一个[示例 .editorconfig 文件](#example-editorconfig-file)。

## <a name="convention-categories"></a>约定类别

有三种受支持的 .NET 编码约定类别：

- [语言代码样式](#language-code-styles)

   与 C# 或 Visual Basic 语言相关的规则。 例如，定义变量或首选 expression-bodied 成员时，可以指定与 `var` 或显式类型的使用相关的规则。

- [格式设置约定](#formatting-conventions)

   与代码的布局和结构有关的规则，其作用是使代码更易于阅读。 例如，可以指定控制块中的 Allman 大括号或首选空格的相关规则。

- [命名约定](../ide/editorconfig-naming-conventions.md)

   与码位元素的命名有关的规则。 例如，可以指定 `async` 方法必须以“Async”结尾。

## <a name="language-code-styles"></a>语言代码样式

语言代码样式的规则具有以下格式：

`options_name = false|true : none|silent|suggestion|warning|error`

对于每个语言代码样式规则，必须指定“true”（以此样式为首选项）或“false”（不以此样式为首选项），以及“严重性”。 “严重性”指定强制执行该样式的级别。

下表列出了可能的严重性值及其效果：

严重性 | 效果
:------- | ------
`none` | 如违反此规则，不会向用户显示任何内容。 但代码生成功能会以此样式生成代码。 “快速操作和重构”菜单中永远不会出现严重性为 `none` 的规则。 大多数情况下，此情况被视为“禁用”或“忽略”。
`silent`（在 Visual Studio 2017 版本 15.8 中也是 `refactoring`） | 如违反此规则，不会向用户显示任何内容。 但代码生成功能会以此样式生成代码。 严重性为 `silent` 的规则参与清理，并在“快速操作和重构”菜单中显示。
`suggestion` | 如违反此样式规则，会将其作为建议向用户显示。 建议显示为前两个字符下的三个灰点。
`warning` | 如违反此样式规则，显示编译器警告。
`error` | 如违反此样式规则，显示编译器错误。

以下列表显示允许的语言代码样式规则：

- .NET 代码样式设置
    - [“This.”和“Me.”限定符](#this_and_me)
        - dotnet\_style\_qualification\_for_field
        - dotnet\_style\_qualification\_for_property
        - dotnet\_style\_qualification\_for_method
        - dotnet\_style\_qualification\_for_event
    - [语言关键字，而非类型引用的框架类型名称](#language_keywords)
        - dotnet\_style\_predefined\_type\_for\_locals\_parameters_members
        - dotnet\_style\_predefined\_type\_for\_member_access
    - [修饰符首选项](#normalize_modifiers)
        - dotnet\_style\_require\_accessibility_modifiers
        - csharp\_preferred\_modifier_order
        - visual\_basic\_preferred\_modifier_order
        - dotnet\_style\_readonly\_field
    - [括号首选项](#parentheses)
        - dotnet\_style\_parentheses\_in\_arithmetic\_binary\_operators
        - dotnet\_style\_parentheses\_in\_other\_binary\_operators
        - dotnet\_style\_parentheses\_in\_other\_operators
        - dotnet\_style\_parentheses\_in\_relational\_binary\_operators
    - [表达式级首选项](#expression_level)
        - dotnet\_style\_object_initializer
        - dotnet\_style\_collection_initializer
        - dotnet\_style\_explicit\_tuple_names
        - dotnet\_style\_prefer\_inferred\_tuple_names
        - dotnet\_style\_prefer\_inferred\_anonymous\_type\_member_names
        - dotnet\_style\_prefer\_auto\_properties
        - dotnet\_style\_prefer\_is\_null\_check\_over\_reference\_equality\_method
        - dotnet\_style\_prefer\_conditional\_expression\_over\_assignment
        - dotnet\_style\_prefer\_conditional\_expression\_over\_return
    - [“NULL”检查首选项](#null_checking)
        - dotnet\_style\_coalesce_expression
        - dotnet\_style\_null_propagation
- C# 代码样式设置
    - [隐式和显式类型](#implicit-and-explicit-types)
        - csharp\_style\_var\_for\_built\_in_types
        - csharp\_style\_var\_when\_type\_is_apparent
        - csharp\_style\_var_elsewhere
    - [Expression-Bodied 成员](#expression_bodied_members)
        - csharp\_style\_expression\_bodied_methods
        - csharp\_style\_expression\_bodied_constructors
        - csharp\_style\_expression\_bodied_operators
        - csharp\_style\_expression\_bodied_properties
        - csharp\_style\_expression\_bodied_indexers
        - csharp\_style\_expression\_bodied_accessors
    - [模式匹配](#pattern_matching)
        - csharp\_style\_pattern\_matching\_over\_is\_with\_cast_check
        - csharp\_style\_pattern\_matching\_over\_as\_with\_null_check
    - [内联变量声明](#inlined_variable_declarations)
        - csharp\_style\_inlined\_variable_declaration
    - [表达式级首选项](#expression_level_csharp)
        - csharp\_prefer\_simple\_default_expression
        - csharp\_style\_deconstructed\_variable_declaration
        - csharp\_style\_pattern\_local\_over\_anonymous_function
    - [“NULL”检查首选项](#null_checking_csharp)
        - csharp\_style\_throw_expression
        - csharp\_style\_conditional\_delegate_call
    - [代码块首选项](#code_block)
        - csharp\_prefer_braces

### <a name="net-code-style-settings"></a>.NET 代码样式设置

本节中的样式规则均适用于 C# 和 Visual Basic。 若要查看以首选编程语言编写的代码示例，请在浏览器窗口右上角的下拉“语言”菜单中选择它。

#### <a name="this_and_me"></a>“This.” 和“Me.” 限定符

此样式规则（规则 ID IDE0003 和 IDE0009）可应用于字段、属性、方法或事件。 值为“true”表示代码符号以 `this.` (C#) 或 `Me.` (Visual Basic) 开头为首选项。 值为“false”表示码位元素不以 `this.` 或 `Me.` 开头为首选项。

下表显示规则名称、适用的编程语言和默认值：

| 规则名称 | 适用的语言 | Visual Studio 默认值 |
| ----------- | -------------------- | ----------------------|
| dotnet_style_qualification_for_field | C# 和 Visual Basic | false:silent |
| dotnet_style_qualification_for_property | C# 和 Visual Basic | false:silent |
| dotnet_style_qualification_for_method | C# 和 Visual Basic | false:silent |
| dotnet_style_qualification_for_event | C# 和 Visual Basic | false:silent |

**dotnet\_style\_qualification\_for_field**

- 如果此规则设置为“true”，则字段以 `this.` (C#) 或 `Me.` (Visual Basic) 开头为首选项。
- 如果此规则设置为“false”，则字段不以 `this.` 或 `Me.` 开头为首选项。

代码示例：

```csharp
// dotnet_style_qualification_for_field = true
this.capacity = 0;

// dotnet_style_qualification_for_field = false
capacity = 0;
```

```vb
' dotnet_style_qualification_for_field = true
Me.capacity = 0

' dotnet_style_qualification_for_field = false
capacity = 0
```

**dotnet\_style\_qualification\_for_property**

- 如果此规则设置为“true”，则属性以 `this.` (C#) 或 `Me.` (Visual Basic) 开头为首选项。
- 如果此规则设置为“false”，则属性不以 `this.` 或 `Me.` 开头为首选项。

代码示例：

```csharp
// dotnet_style_qualification_for_property = true
this.ID = 0;

// dotnet_style_qualification_for_property = false
ID = 0;
```

```vb
' dotnet_style_qualification_for_property = true
Me.ID = 0

' dotnet_style_qualification_for_property = false
ID = 0
```

**dotnet\_style\_qualification\_for_method**

- 如果此规则设置为“true”，则方法以 `this.` (C#) 或 `Me.` (Visual Basic) 开头为首选项。
- 如果此规则设置为“false”，则方法不以 `this.` 或 `Me.` 开头为首选项。

代码示例：

```csharp
// dotnet_style_qualification_for_method = true
this.Display();

// dotnet_style_qualification_for_method = false
Display();
```

```vb
' dotnet_style_qualification_for_method = true
Me.Display()

' dotnet_style_qualification_for_method = false
Display()
```

**dotnet\_style\_qualification\_for_event**

- 如果此规则设置为“true”，则事件以 `this.` (C#) 或 `Me.` (Visual Basic) 开头为首选项。
- 如果此规则设置为“false”，则事件不以 `this.` 或 `Me.` 开头为首选项。

代码示例：

```csharp
// dotnet_style_qualification_for_event = true
this.Elapsed += Handler;

// dotnet_style_qualification_for_event = false
Elapsed += Handler;
```

```vb
' dotnet_style_qualification_for_event = true
AddHandler Me.Elapsed, AddressOf Handler

' dotnet_style_qualification_for_event = false
AddHandler Elapsed, AddressOf Handler
```

这些规则可在 .editorconfig 文件中以如下方式出现：

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_qualification_for_field = false:suggestion
dotnet_style_qualification_for_property = false:suggestion
dotnet_style_qualification_for_method = false:suggestion
dotnet_style_qualification_for_event = false:suggestion
```

#### <a name="language_keywords"></a>语言关键字，而非类型引用的框架类型名称

此样式规则可应用到本地变量、方法参数和类成员，也可作为针对类型成员访问表达式的单独规则。 值为“true”表示，如果类型中有用于表示类型的关键字，首选语言关键字（例如 `int` 或 `Integer`），而不是类型名称（例如 `Int32`）。 值为“false”代表类型名称为首选项，而非语言关键字。

下表显示规则名称、规则 ID、适用的编程语言和默认值：

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 |
| --------- | ------- | -------------------- | ----------------------|
| dotnet_style_predefined_type_for_locals_parameters_members | IDE0012 和 IDE0014 | C# 和 Visual Basic | true:silent |
| dotnet_style_predefined_type_for_member_access | IDE0013 和 IDE0015 | C# 和 Visual Basic | true:silent |

**dotnet\_style\_predefined\_type\_for\_locals\_parameters_members**

- 如果此规则设置为“true”，则对于类型（其中具有用于表示该类型的关键字），本地变量、方法参数和类成员的语言关键字为首选项，而非类型名称。
- 如果此规则设置为“false”，则本地变量、方法参数和类成员的类型名称为首选项，而非语言关键字。

代码示例：

```csharp
// dotnet_style_predefined_type_for_locals_parameters_members = true
private int _member;

// dotnet_style_predefined_type_for_locals_parameters_members = false
private Int32 _member;
```

```vb
' dotnet_style_predefined_type_for_locals_parameters_members = true
Private _member As Integer

' dotnet_style_predefined_type_for_locals_parameters_members = false
Private _member As Int32
```

**dotnet\_style\_predefined\_type\_for\_member_access**

- 如果此规则设置为“true”，则对于类型（其中具有用于表示该类型的关键字），成员访问表达式的语言关键字为首选项，而非类型名称。
- 如果此规则设置为“false”，则成员访问表达式的类型名称为首选项，而非语言关键字。

代码示例：

```csharp
// dotnet_style_predefined_type_for_member_access = true
var local = int.MaxValue;

// dotnet_style_predefined_type_for_member_access = false
var local = Int32.MaxValue;
```

```vb
' dotnet_style_predefined_type_for_member_access = true
Dim local = Integer.MaxValue

' dotnet_style_predefined_type_for_member_access = false
Dim local = Int32.MaxValue
```

这些规则可在 .editorconfig 文件中以如下方式出现：

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_predefined_type_for_locals_parameters_members = true:suggestion
dotnet_style_predefined_type_for_member_access = true:suggestion
```

#### <a name="normalize_modifiers"></a>修饰符首选项

本部分中的样式规则与修饰符首选项相关，包括要求使用可访问性修饰符、指定所需的修饰符排序顺序以及要求使用只读修饰符。

下表显示规则名称、规则 ID、适用的编程语言、默认值和第一个支持的 Visual Studio 版本：

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | Visual Studio 2017 版本 |
| --------- | ------- | -------------------- | ----------------------| ---------------- |
| dotnet_style_require_accessibility_modifiers | IDE0040 | C# 和 Visual Basic | for_non_interface_members:silent | 15.5 |
| csharp_preferred_modifier_order | IDE0036 | C# | public、private、protected、internal、static、extern、new、virtual、abstract、sealed、override、readonly、unsafe、volatile、async:silent | 15.5 |
| visual_basic_preferred_modifier_order | IDE0036 | Visual Basic | Partial、Default、Private、Protected、Public、Friend、NotOverridable、Overridable、MustOverride、Overloads、Overrides、MustInherit、NotInheritable、Static、Shared、Shadows、ReadOnly、WriteOnly、Dim、Const、WithEvents、Widening、Narrowing、Custom、Async:silent | 15.5 |
| dotnet_style_readonly_field | IDE0044 | C# 和 Visual Basic | true:suggestion | 15.7 |

**dotnet\_style\_require\_accessibility_modifiers**

此规则接受下表中的一个值：

| 值 | 说明 |
| ----- |:----------- |
| always | 优先指定可访问性修饰符 |
| for\_non\_interface_members | 优先声明可访问性修饰符，公共接口成员除外。 （这与往常相同，并且已添加以用于未来验证（如果 C# 添加默认接口方法）。） |
| never | 不优先指定可访问性修饰符 |
| omit_if_default | 优先指定可访问性修饰符（除非它们是默认修饰符） |

代码示例：

```csharp
// dotnet_style_require_accessibility_modifiers = always
// dotnet_style_require_accessibility_modifiers = for_non_interface_members
class MyClass
{
    private const string thisFieldIsConst = "constant";
}

// dotnet_style_require_accessibility_modifiers = never
class MyClass
{
    const string thisFieldIsConst = "constant";
}
```

**csharp_preferred_modifier_order**

- 如果对一系列修饰符设置该规则，则首选指定的排序。
- 如果文件中省略了此规则，则不优先使用修饰符顺序。

代码示例：

```csharp
// csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async
class MyClass
{
    private static readonly int _daysInYear = 365;
}
```

**visual_basic_preferred_modifier_order**

- 如果对一系列修饰符设置该规则，则首选指定的排序。
- 如果文件中省略了此规则，则不优先使用修饰符顺序。

代码示例：

```vb
' visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async
Public Class MyClass
    Private Shared ReadOnly daysInYear As Int = 365
End Class
```

**dotnet_style_readonly_field**

- 如果此规则设置为 true，则偏向标记为 `readonly` (C#) 或 `ReadOnly` (Visual Basic) 的字段，如果它们只是内联分配或者在构造函数中的话。
- 如果此规则设置为 false，则就字段是否应标记为 `readonly` (C#) 或 `ReadOnly` (Visual Basic) 无偏向。

代码示例：

```csharp
// dotnet_style_readonly_field = true
class MyClass
{
    private readonly int _daysInYear = 365;
}
```

```vb
' dotnet_style_readonly_field = true
Public Class MyClass
    Private ReadOnly daysInYear As Int = 365
End Class
```

这些规则可在 .editorconfig 文件中以如下方式出现：

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_require_accessibility_modifiers = always:suggestion
dotnet_style_readonly_field = true:warning

# CSharp code style settings:
[*.cs]
csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async:suggestion

# Visual Basic code style settings:
[*.vb]
visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async:suggestion
```

#### <a name="parentheses"></a>括号首选项

本部分中的样式规则涉及括号首选项，包括算术、关系和其他二元运算符的括号使用情况。

下表显示规则名称、规则 ID、适用的编程语言、默认值和第一个支持的 Visual Studio 版本：

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | Visual Studio 2017 版本 |
| --------- | ------- | -------------------- | ----------------------| ---- |
| dotnet_style_parentheses_in_arithmetic_binary_operators | IDE0047 | C# 和 Visual Basic | always_for_clarity:silent | 15.8 |
| dotnet_style_parentheses_in_relational_binary_operators | IDE0047 | C# 和 Visual Basic | always_for_clarity:silent | 15.8 |
| dotnet_style_parentheses_in_other_binary_operators | IDE0047 | C# 和 Visual Basic | always_for_clarity:silent | 15.8 |
| dotnet_style_parentheses_in_other_operators | IDE0047 | C# 和 Visual Basic | never_if_unnecessary:silent | 15.8 |

**dotnet\_style\_parentheses\_in\_arithmetic\_binary_operators**

- 当此规则设置为 always_for_clarity 时，请首选括号以指定算术运算符（`*`、`/`、`%`、`+`、`-`、`<<`、`>>`、`&`、`^`、`|`）的优先级。
- 当此规则设置为 never_if_unnecessary，且算术运算符（`*`、`/`、`%`、`+`、`-`、`<<`、`>>`、`&`、`^`、`|`）的优先级显而易见时，最好不要使用括号。

代码示例：

```csharp
// dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity
var v = a + (b * c);

// dotnet_style_parentheses_in_arithmetic_binary_operators = never_if_unnecessary
var v = a + b * c;
```

```vb
' dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity
Dim v = a + (b * c)

' dotnet_style_parentheses_in_arithmetic_binary_operators = never_if_unnecessary
Dim v = a + b * c
```

**dotnet\_style\_parentheses\_in\_relational\_binary_operators**

- 如果此规则设置为 always_for_clarity，首选括号来指定关系运算符（`>`、`<`、`<=`、`>=`、`is`、`as`、`==`、`!=`）优先级。
- 当此规则设置为 never_if_unnecessary，且关系运算符（`>`、`<`、`<=`、`>=`、`is`、`as`、`==`、`!=`）的优先级显而易见时，最好不要使用括号。

代码示例：

```csharp
// dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity
var v = (a < b) == (c > d);

// dotnet_style_parentheses_in_relational_binary_operators = never_if_unnecessary
var v = a < b == c > d;
```

```vb
' dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity
Dim v = (a < b) = (c > d)

' dotnet_style_parentheses_in_relational_binary_operators = never_if_unnecessary
Dim v = a < b = c > d
```

**dotnet\_style\_parentheses\_in\_other\_binary_operators**

- 当此规则设置为 always_for_clarity 时，请首选括号以指定其他二元运算符（`&&`、`||`、`??`）的优先级。
- 当此规则设置为 never_if_unnecessary，且其他二元运算符（`&&`、`||`、`??`）的优先级显而易见时，最好不要使用括号。

代码示例：

```csharp
// dotnet_style_parentheses_in_other_binary_operators = always_for_clarity
var v = a || (b && c);

// dotnet_style_parentheses_in_other_binary_operators = never_if_unnecessary
var v = a || b && c;
```

```vb
' dotnet_style_parentheses_in_other_binary_operators = always_for_clarity
Dim v = a OrElse (b AndAlso c)

' dotnet_style_parentheses_in_other_binary_operators = never_if_unnecessary
Dim v = a OrElse b AndAlso c
```

**dotnet\_style\_parentheses\_in\_other_operators**

- 当此规则设置为 always_for_clarity 时，请首选括号以指定运算符优先级。
- 当此规则设置为 never_if_unnecessary，且运算符的优先级显而易见时，最好不要使用括号。

代码示例：

```csharp
// dotnet_style_parentheses_in_other_operators = always_for_clarity
var v = (a.b).Length;

// dotnet_style_parentheses_in_other_operators = never_if_unnecessary
var v = a.b.Length;
```

```vb
' dotnet_style_parentheses_in_other_operators = always_for_clarity
Dim v = (a.b).Length

' dotnet_style_parentheses_in_other_operators = never_if_unnecessary
Dim v = a.b.Length
```

这些规则可在 .editorconfig 文件中以如下方式出现：

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_other_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_other_operators = never_if_unnecessary:silent
```

#### <a name="expression_level"></a>表达式级首选项

本节中的样式规则与表达式级别首选项有关，包括对象初始值设定项、集合初始值设定项、显式或推断元组名称和推断匿名类型的使用。

下表显示规则名称、规则 ID、适用的编程语言、默认值和第一个支持的 Visual Studio 版本：

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | Visual Studio 2017 版本 |
| --------- | ------- | -------------------- | ----------------------| ---- |
| dotnet_style_object_initializer | IDE0017 | C# 和 Visual Basic | true:suggestion | 首次发布 |
| dotnet_style_collection_initializer | IDE0028 | C# 和 Visual Basic | true:suggestion | 首次发布 |
| dotnet_style_explicit_tuple_names | IDE0033 | C# 7.0+ 和 Visual Basic 15+ | true:suggestion | 首次发布 |
| dotnet_style_prefer_inferred_tuple_names | IDE0037 | C# 7.1+ 和 Visual Basic 15+ | true:suggestion | 15.6 |
| dotnet_style_prefer_inferred_anonymous_type_member_names | IDE0037 | C# 和 Visual Basic | true:suggestion | 15.6 |
| dotnet_style_prefer_auto_properties | IDE0032 | C# 和 Visual Basic | true:silent | 15.7 |
| dotnet_style_prefer_is_null_check_over_reference_equality_method | IDE0041 | C# 和 Visual Basic | true:suggestion | 15.7 |
| dotnet_style_prefer_conditional_expression_over_assignment | IDE0045 | C# 和 Visual Basic | true:silent | 15.8 |
| dotnet_style_prefer_conditional_expression_over_return | IDE0046 | C# 和 Visual Basic | true:silent | 15.8 |

**dotnet\_style\_object_initializer**

- 如果此规则设置为“true”，则使用对象初始值设定项来初始化对象为首选项（如可能）。
- 如果此规则设置为“false”，则不使用对象初始值设定项来初始化对象为首选项。

代码示例：

```csharp
// dotnet_style_object_initializer = true
var c = new Customer() { Age = 21 };

// dotnet_style_object_initializer = false
var c = new Customer();
c.Age = 21;
```

```vb
' dotnet_style_object_initializer = true
Dim c = New Customer() With {.Age = 21}

' dotnet_style_object_initializer = false
Dim c = New Customer()
c.Age = 21
```

**dotnet\_style\_collection_initializer**

- 如果此规则设置为“true”，则使用集合初始值设定项来初始化集合为首选项（如可能）。
- 如果此规则设置为“false”，则不使用集合初始值设定项来初始化集合为首选项。

代码示例：

```csharp
// dotnet_style_collection_initializer = true
var list = new List<int> { 1, 2, 3 };

// dotnet_style_collection_initializer = false
var list = new List<int>();
list.Add(1);
list.Add(2);
list.Add(3);
```

```vb
' dotnet_style_collection_initializer = true
Dim list = New List(Of Integer) From {1, 2, 3}

' dotnet_style_collection_initializer = false
Dim list = New List(Of Integer)
list.Add(1)
list.Add(2)
list.Add(3)
```

**dotnet\_style\_explicit\_tuple_names**

- 如果此规则设置为“true”，则元组名称为首选项，而非 ItemX 属性。
- 如果此规则设置为“false”，则 ItemX 属性为首选项，而非元组名称。

代码示例：

```csharp
// dotnet_style_explicit_tuple_names = true
(string name, int age) customer = GetCustomer();
var name = customer.name;

// dotnet_style_explicit_tuple_names = false
(string name, int age) customer = GetCustomer();
var name = customer.Item1;
```

```vb
 ' dotnet_style_explicit_tuple_names = true
Dim customer As (name As String, age As Integer) = GetCustomer()
Dim name = customer.name

' dotnet_style_explicit_tuple_names = false
Dim customer As (name As String, age As Integer) = GetCustomer()
Dim name = customer.Item1
```

dotnet\_style\_prefer\_inferred\_tuple_names

- 此规则设置为 true 时，首选推断元组元素名称。
- 此规则设置为 false 时，首选显式元组元素名称。

代码示例：

```csharp
// dotnet_style_prefer_inferred_tuple_names = true
var tuple = (age, name);

// dotnet_style_prefer_inferred_tuple_names = false
var tuple = (age: age, name: name);
```

```vb
' dotnet_style_prefer_inferred_tuple_names = true
Dim tuple = (name, age)

' dotnet_style_prefer_inferred_tuple_names = false
Dim tuple = (name:=name, age:=age)
```

**dotnet\_style\_prefer\_inferred\_anonymous\_type\_member_names**

- 此规则设置为 true 时，首选推断匿名类型成员名称。
- 此规则设置为 false 时，首选显式匿名类型成员名称。

代码示例：

```csharp
// dotnet_style_prefer_inferred_anonymous_type_member_names = true
var anon = new { age, name };

// dotnet_style_prefer_inferred_anonymous_type_member_names = false
var anon = new { age = age, name = name };
```

```vb
' dotnet_style_prefer_inferred_anonymous_type_member_names = true
Dim anon = New With {name, age}

' dotnet_style_prefer_inferred_anonymous_type_member_names = false
Dim anon = New With {.name = name, .age = age}
```

**dotnet\_style\_prefer\_auto\_properties**

- 如果此规则设置为“true”，首选自动属性，而不是包含专用支持字段的属性。
- 如果此规则设置为“false”，首选包含专用支持字段的属性，而不是自动属性。

代码示例：

```csharp
// dotnet_style_prefer_auto_properties = true
private int Age { get; }

// dotnet_style_prefer_auto_properties = false
private int age;

public int Age
{
    get
    {
        return age;
    }
}
```

```vb
' dotnet_style_prefer_auto_properties = true
Public ReadOnly Property Age As Integer

' dotnet_style_prefer_auto_properties = false
Private _age As Integer

Public ReadOnly Property Age As Integer
    Get
        return _age
    End Get
End Property
```

**dotnet\_style\_prefer\_is\_null\_check\_over\_reference\_equality\_method**

- 如果将此规则设置为 true，则首选使用含匹配模式的 NULL 检查，而非 object.ReferenceEquals。
- 如果将此规则设置为 false，则首选 object.ReferenceEquals，而非使用含匹配模式的 NULL 检查。

代码示例：

```csharp
// dotnet_style_prefer_is_null_check_over_reference_equality_method = true
if (value is null)
    return;

// dotnet_style_prefer_is_null_check_over_reference_equality_method = false
if (object.ReferenceEquals(value, null))
    return;
```

```vb
' dotnet_style_prefer_is_null_check_over_reference_equality_method = true
If value Is Nothing
    Return
End If

' dotnet_style_prefer_is_null_check_over_reference_equality_method = false
If Object.ReferenceEquals(value, Nothing)
    Return
End If
```

**dotnet\_style\_prefer\_conditional\_expression\_over_assignment**

- 当此规则设置为 true 时，与 if-else 语句相比，首选三元条件进行赋值。
- 当此规则设置为 false 时，与三元条件相比，首先 if-else 语句进行赋值。

代码示例：

```csharp
// dotnet_style_prefer_conditional_expression_over_assignment = true
string s = expr ? "hello" : "world";

// dotnet_style_prefer_conditional_expression_over_assignment = false
string s;
if (expr)
{
    s = "hello";
}
else
{
    s = "world";
}
```

```vb
' dotnet_style_prefer_conditional_expression_over_assignment = true
Dim s As String = If(expr, "hello", "world")

' dotnet_style_prefer_conditional_expression_over_assignment = false
Dim s As String
If expr Then
    s = "hello"
Else
    s = "world"
End If
```

**dotnet\_style\_prefer\_conditional\_expression\_over_return**

- 当此规则设置为 true 时，与 if-else 语句相比，return 语句首选三元条件。
- 当此规则设置为 false 时，与三元条件相比，return 语句首选 if-else 语句。

代码示例：

```csharp
// dotnet_style_prefer_conditional_expression_over_return = true
return expr ? "hello" : "world"

// dotnet_style_prefer_conditional_expression_over_return = false
if (expr)
{
    return "hello";
}
else
{
    return "world";
}
```

```vb
' dotnet_style_prefer_conditional_expression_over_return = true
Return If(expr, "hello", "world")

' dotnet_style_prefer_conditional_expression_over_return = false
If expr Then
    Return "hello"
Else
    Return "world"
End If
```

这些规则可在 .editorconfig 文件中以如下方式出现：

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_object_initializer = true:suggestion
dotnet_style_collection_initializer = true:suggestion
dotnet_style_explicit_tuple_names = true:suggestion
dotnet_style_prefer_inferred_tuple_names = true:suggestion
dotnet_style_prefer_inferred_anonymous_type_member_names = true:suggestion
dotnet_style_prefer_auto_properties = true:silent
dotnet_style_prefer_conditional_expression_over_assignment = true:suggestion
dotnet_style_prefer_conditional_expression_over_return = true:suggestion
```

#### <a name="null_checking"></a>Null 检查首选项

本节中的样式规则与 Null 检查首选项有关。

下表显示规则名称、规则 ID、适用的编程语言、默认值和第一个支持的 Visual Studio 版本：

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | Visual Studio 2017 版本 |
| --------- | ------- | -------------------- | ----------------------| ---- |
| dotnet_style_coalesce_expression | IDE0029 | C# 和 Visual Basic | true:suggestion | 首次发布 |
| dotnet_style_null_propagation | IDE0031 | C# 6.0+ 和 Visual Basic 14+ | true:suggestion | 首次发布 |

**dotnet\_style\_coalesce_expression**

- 如果此规则设置为“true”，则 NULL 合并表达式为首选项，而非三元运算符检查。
- 如果此规则设置为“false”，则三元运算符检查为首选项，而非 NULL 合并表达式。

代码示例：

```csharp
// dotnet_style_coalesce_expression = true
var v = x ?? y;

// dotnet_style_coalesce_expression = false
var v = x != null ? x : y; // or
var v = x == null ? y : x;
```

```vb
' dotnet_style_coalesce_expression = true
Dim v = If(x, y)

' dotnet_style_coalesce_expression = false
Dim v = If(x Is Nothing, y, x) ' or
Dim v = If(x IsNot Nothing, x, y)
```

**dotnet\_style\_null_propagation**

- 如果此规则设置为“true”，则使用 NULL 条件运算符（若可能）为首选项。
- 如果此规则设置为“false”，则使用三元 NULL 检查（若可能）为首选项。

代码示例：

```csharp
// dotnet_style_null_propagation = true
var v = o?.ToString();

// dotnet_style_null_propagation = false
var v = o == null ? null : o.ToString(); // or
var v = o != null ? o.String() : null;
```

```vb
' dotnet_style_null_propagation = true
Dim v = o?.ToString()

' dotnet_style_null_propagation = false
Dim v = If(o Is Nothing, Nothing, o.ToString()) ' or
Dim v = If(o IsNot Nothing, o.ToString(), Nothing)
```

这些规则可在 .editorconfig 文件中以如下方式出现：

```EditorConfig
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_coalesce_expression = true:suggestion
dotnet_style_null_propagation = true:suggestion
```

### <a name="c-code-style-settings"></a>C# 代码样式设置

本节中的样式规则仅适用于 C#。

#### <a name="implicit-and-explicit-types"></a>隐式和显式类型

本节中的样式规则（规则 ID 为 IDE0007 和 IDE0008）与变量声明中的 [var](/dotnet/csharp/language-reference/keywords/var) 关键字和显式类型的使用有关。 此规则可单独应用于内置类型（前提是该类型为明显）和其他情况。

下表显示规则名称、适用的编程语言和默认值：

| 规则名称 | 适用的语言 | Visual Studio 默认值 |
| ----------- | -------------------- | ----------------------|
| csharp_style_var_for_built_in_types | C# | true:silent |
| csharp_style_var_when_type_is_apparent | C# | true:silent |
| csharp_style_var_elsewhere | C# | true:silent |

**csharp\_style\_var\_for\_built\_in_types**

- 如果此规则设置为“true”，则使用 `var` 声明 `int` 等内置系统类型的变量为首选项。
- 如果此规则设置为“false”，则使用显示类型声明 `int` 等内置系统类型的变量为首选项，而非使用 `var`。

代码示例：

```csharp
// csharp_style_var_for_built_in_types = true
var x = 5;

// csharp_style_var_for_built_in_types = false
int x = 5;
```

**csharp\_style\_var\_when\_type\_is_apparent**

- 如果此规则设置为“true”，则声明表达式右侧已提到该类型时，使用 `var` 为首选项。
- 如果此规则设置为“false”，则声明表达式右侧已提到该类型时，使用显式类型为首选项，而非 `var`。

代码示例：

```csharp
// csharp_style_var_when_type_is_apparent = true
var obj = new Customer();

// csharp_style_var_when_type_is_apparent = false
Customer obj = new Customer();
```

**csharp\_style\_var_elsewhere**

- 如果此规则设置为“true”，则在任何情况下，`var` 为首选项，而非显式类型，除非由另一个代码样式规则替代。
- 如果此规则设置为“false”，则在任何情况下，显式类型为首选项，而非 `var`，除非由另一个代码样式规则替代。

代码示例：

```csharp
// csharp_style_var_elsewhere = true
var f = this.Init();

// csharp_style_var_elsewhere = false
bool f = this.Init();
```

.editorconfig 文件示例：

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_var_for_built_in_types = true:suggestion
csharp_style_var_when_type_is_apparent = true:suggestion
csharp_style_var_elsewhere = true:suggestion
```

#### <a name="expression_bodied_members"></a>Expression-bodied 成员

本节中的样式规则与在逻辑由单个表达式组成的情况下，[expression-bodied 成员](/dotnet/csharp/programming-guide/statements-expressions-operators/expression-bodied-members)的使用有关。 此规则可应用于方法、构造函数、运算符、属性、索引器和访问器。

下表显示规则名称、规则 ID、适用的语言版本、默认值和第一个支持的 Visual Studio 版本：

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | Visual Studio 2017 版本 |
| --------- | ------- | -------------------- | ----------------------| ---------------- |
| csharp_style_expression_bodied_methods | IDE0022 | C# 6.0+ | false:silent | 15.3 |
| csharp_style_expression_bodied_constructors | IDE0021 | C# 7.0+ | false:silent | 15.3 |
| csharp_style_expression_bodied_operators | IDE0023 和 IDE0024 | C# 7.0+ | false:silent | 15.3 |
| csharp_style_expression_bodied_properties | IDE0025 | C# 7.0+ | true:silent | 15.3 |
| csharp_style_expression_bodied_indexers | IDE0026 | C# 7.0+ | true:silent | 15.3 |
| csharp_style_expression_bodied_accessors | IDE0027 | C# 7.0+ | true:silent | 15.3 |

**csharp\_style\_expression\_bodied_methods**

此规则接受下表中的值：

| 值 | 说明 |
| ----- |:----------- |
| true | 倾向于使用方法的 expression-bodied 成员 |
| when_on_single_line | 当其将为单行时，优先使用方法的 expression-bodied 成员 |
| False | 优先选择方法的块主体 |

代码示例：

```csharp
// csharp_style_expression_bodied_methods = true
public int GetAge() => this.Age;

// csharp_style_expression_bodied_methods = false
public int GetAge() { return this.Age; }
```

**csharp\_style\_expression\_bodied_constructors**

此规则接受下表中的值：

| 值 | 说明 |
| ----- |:----------- |
| true | 倾向于使用构造函数的 expression-bodied 成员 |
| when_on_single_line | 当其将为单行时，倾向于使用构造函数的 expression-bodied 成员 |
| False | 倾向于使用构造函数的块主体 |

代码示例：

```csharp
// csharp_style_expression_bodied_constructors = true
public Customer(int age) => Age = age;

// csharp_style_expression_bodied_constructors = false
public Customer(int age) { Age = age; }
```

**csharp\_style\_expression\_bodied_operators**

此规则接受下表中的值：

| 值 | 说明 |
| ----- |:----------- |
| true | 倾向于使用运算符的 expression-bodied 成员 |
| when_on_single_line | 当其将为单行时，倾向于使用运算符的 expression-bodied 成员 |
| False | 倾向于使用运算符的块主体 |

代码示例：

```csharp
// csharp_style_expression_bodied_operators = true
public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
    => new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary);

// csharp_style_expression_bodied_operators = false
public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
{ return new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary); }
```

**csharp\_style\_expression\_bodied_properties**

此规则接受下表中的值：

| 值 | 说明 |
| ----- |:----------- |
| true | 倾向于使用属性的 expression-bodied 成员 |
| when_on_single_line | 当其将为单行时，倾向于使用属性的 expression-bodied 成员 |
| False | 倾向于使用属性的块主体 |

代码示例：

```csharp
// csharp_style_expression_bodied_properties = true
public int Age => _age;

// csharp_style_expression_bodied_properties = false
public int Age { get { return _age; }}
```

**csharp\_style\_expression\_bodied_indexers**

此规则接受下表中的值：

| 值 | 说明 |
| ----- |:----------- |
| true | 倾向于使用索引器的 expression-bodied 成员 |
| when_on_single_line | 当其将为单行时，倾向于使用索引器的 expression-bodied 成员 |
| False | 倾向于使用索引器的块主体 |

代码示例：

```csharp
// csharp_style_expression_bodied_indexers = true
public T this[int i] => _values[i];

// csharp_style_expression_bodied_indexers = false
public T this[int i] { get { return _values[i]; } }
```

**csharp\_style\_expression\_bodied_accessors**

此规则接受下表中的值：

| 值 | 说明 |
| ----- |:----------- |
| true | 倾向于使用访问器的 expression-bodied 成员 |
| when_on_single_line | 当其将为单行时，倾向于使用访问器的 expression-bodied 成员 |
| False | 倾向于使用访问器的块主体 |

代码示例：

```csharp
// csharp_style_expression_bodied_accessors = true
public int Age { get => _age; set => _age = value; }

// csharp_style_expression_bodied_accessors = false
public int Age { get { return _age; } set { _age = value; } }
```

.editorconfig 文件示例：

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_methods = false:silent
csharp_style_expression_bodied_constructors = false:silent
csharp_style_expression_bodied_operators = false:silent
csharp_style_expression_bodied_properties = true:suggestion
csharp_style_expression_bodied_indexers = true:suggestion
csharp_style_expression_bodied_accessors = true:suggestion
```

#### <a name="pattern_matching"></a>模式匹配

本节中的样式规则与 C# 中[模式匹配](/dotnet/csharp/pattern-matching)的使用有关。

下表显示规则名称、规则 ID、适用的语言版本和默认值：

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 |
| --------- | ------- | -------------------- | ----------------------|
| csharp_style_pattern_matching_over_is_with_cast_check | IDE0020 | C# 7.0+ | true:suggestion |
| csharp_style_pattern_matching_over_as_with_null_check | IDE0019 | C# 7.0+ | true:suggestion |

**csharp\_style\_pattern\_matching\_over\_is\_with\_cast_check**

- 如果此规则设置为“true”，则模式匹配为首选项，而非带类型强制转换的 `is` 表达式。
- 如果此规则设置为“false”，则带类型强制转换的 `is` 表达式为首选项，而非模式匹配。

代码示例：

```csharp
// csharp_style_pattern_matching_over_is_with_cast_check = true
if (o is int i) {...}

// csharp_style_pattern_matching_over_is_with_cast_check = false
if (o is int) {var i = (int)o; ... }
```

**csharp\_style\_pattern\_matching\_over\_as\_with\_null_check**

- 如果此规则设置为“true”，则使用模式匹配确定内容是否为某个特定类型为首选项，而非使用带 NULL 检查的 `as` 表达式。
- 如果此规则设置为“false”，则使用带 NULL 检查的 `as` 表达式确定内容是否为某个特定类型为首选项，而非使用模式匹配。

代码示例：

```csharp
// csharp_style_pattern_matching_over_as_with_null_check = true
if (o is string s) {...}

// csharp_style_pattern_matching_over_as_with_null_check = false
var s = o as string;
if (s != null) {...}
```

.editorconfig 文件示例：

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_pattern_matching_over_is_with_cast_check = true:suggestion
csharp_style_pattern_matching_over_as_with_null_check = true:suggestion
```

#### <a name="inlined_variable_declarations"></a>内联变量声明

此样式规则与 `out` 变量是否声明为内联有关。 从 C# 7 开始，可以[在方法调用的实际参数列表中声明 out 变量](/dotnet/csharp/language-reference/keywords/out-parameter-modifier#calling-a-method-with-an-out-argument)，而不是在单独的变量声明中。

下表显示规则名称、规则 ID、适用的语言版本和默认值：

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 |
| --------- | -------- | -------------------- | ----------------------|
| csharp_style_inlined_variable_declaration | IDE0018 | C# 7.0+ | true:suggestion |

**csharp\_style\_inlined\_variable_declaration**

- 如果此规则设置为“true”，则 `out` 变量在方法调用的参数列表中声明为内联为首选项（如可能）。
- 如果此规则设置为“false”，则在方法调用之前声明 `out` 变量为首选项。

代码示例：

```csharp
// csharp_style_inlined_variable_declaration = true
if (int.TryParse(value, out int i) {...}

// csharp_style_inlined_variable_declaration = false
int i;
if (int.TryParse(value, out i) {...}
```

.editorconfig 文件示例：

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_inlined_variable_declaration = true:suggestion
```

#### <a name="expression_level_csharp"></a>表达式级首选项

本部分的样式规则与表达式级首选项相关，包括使用[默认表达式](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference)、析构变量和本地函数（优先于匿名函数）。

下表显示规则名称、规则 ID、适用的语言版本、默认值和第一个支持的 Visual Studio 版本：

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | Visual Studio 2017 版本 |
| --------- | ------- | -------------------- | ----------------------| ---------------- |
| csharp_prefer_simple_default_expression | IDE0034 | C# 7.1+ | true:suggestion | 15.3 |
| csharp_style_deconstructed_variable_declaration | IDE0042 | C# 7.0+ | true:suggestion | 15.5 |
| csharp_style_pattern_local_over_anonymous_function | IDE0039 | C# 7.0+ | true:suggestion | 15.5 |

**csharp\_prefer\_simple\_default_expression**

此样式规则与在编译器可以推断表达式类型的情况下，[默认值表达式的 `default` 文本](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference)的使用有关。

- 如果此规则设置为“true”，则 `default` 为首选项，而非 `default(T)`。
- 如果此规则设置为“false”，则 `default(T)` 为首选项，而非 `default`。

代码示例：

```csharp
// csharp_prefer_simple_default_expression = true
void DoWork(CancellationToken cancellationToken = default) { ... }

// csharp_prefer_simple_default_expression = false
void DoWork(CancellationToken cancellationToken = default(CancellationToken)) { ... }
```

**csharp\_style\_deconstructed\_variable_declaration**

- 如果此规则设置为“true”，则首选析构变量声明。
- 如果此规则设置为“false”，则不首选变量声明中的析构。

代码示例：

```csharp
// csharp_style_deconstructed_variable_declaration = true
var (name, age) = GetPersonTuple();
Console.WriteLine($"{name} {age}");

(int x, int y) = GetPointTuple();
Console.WriteLine($"{x} {y}");

// csharp_style_deconstructed_variable_declaration = false
var person = GetPersonTuple();
Console.WriteLine($"{person.name} {person.age}");

(int x, int y) point = GetPointTuple();
Console.WriteLine($"{point.x} {point.y}");
```

**csharp\_style\_pattern\_local\_over\_anonymous_function**

- 如果此规则设置为“true”，则首选本地函数，而非匿名函数。
- 当此规则设置为“false”，则首选匿名函数，而不是本地函数。

代码示例：

```csharp
// csharp_style_pattern_local_over_anonymous_function = true
int fibonacci(int n)
{
    return n <= 1 ? 1 : fibonacci(n-1) + fibonacci(n-2);
}

// csharp_style_pattern_local_over_anonymous_function = false
Func<int, int> fibonacci = null;
fibonacci = (int n) =>
{
    return n <= 1 ? 1 : fibonacci(n - 1) + fibonacci(n - 2);
};
```

.editorconfig 文件示例：

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_prefer_simple_default_expression = true:suggestion
csharp_style_deconstructed_variable_declaration = true:suggestion
csharp_style_pattern_local_over_anonymous_function = true:suggestion
```

#### <a name="null_checking_csharp"></a>“NULL”检查首选项

这些样式规则与 `null` 检查的相关语法有关，包括 `throw` 表达式或 `throw` 语句的使用，以及调用 [lambda 表达式](/dotnet/csharp/lambda-expressions)时是否执行 NULL 检查或使用条件合并运算符 (`?.`)。

下表显示规则名称、规则 ID、适用的语言版本和默认值：

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 |
| --------- | ------- | -------------------- | ----------------------|
| csharp_style_throw_expression | IDE0016 | C# 7.0+ | true:suggestion |
| csharp_style_conditional_delegate_call | IDE0041 | C# 6.0+ | true:suggestion |

**csharp\_style\_throw_expression**

- 如果此规则设置为“true”，则使用 `throw` 表达式为首选项，而非使用 `throw` 语句。
- 如果此规则设置为“false”，则使用 `throw` 语句为首选项，而非使用 `throw` 表达式。

代码示例：

```csharp
// csharp_style_throw_expression = true
this.s = s ?? throw new ArgumentNullException(nameof(s));

// csharp_style_throw_expression = false
if (s == null) { throw new ArgumentNullException(nameof(s)); }
this.s = s;
```

**csharp\_style\_conditional\_delegate_call**

- 如果此规则设置为“true”，则在调用 Lambda 表达式时使用条件合并运算符 (`?.`) 为首选项，而非执行 NULL 检查。
- 如果此规则设置为“false”，则在调用 Lambda 表达式之前执行 NULL 检查为首选项，而非使用条件合并运算符 (`?.`)。

代码示例：

```csharp
// csharp_style_conditional_delegate_call = true
func?.Invoke(args);

// csharp_style_conditional_delegate_call = false
if (func != null) { func(args); }
```

.editorconfig 文件示例：

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_style_throw_expression = true:suggestion
csharp_style_conditional_delegate_call = false:suggestion
```

#### <a name="code_block"></a>代码块首选项

此样式规则与是否使用大括号 `{ }` 将代码块括起来有关。

下表显示规则名称、规则 ID、适用的语言版本、默认值和第一个支持的 Visual Studio 版本：

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | Visual Studio 2017 版本 |
| --------- | ------- | -------------------- | ----------------------| ---------------- |
| csharp_prefer_braces | IDE0011 | C# | true:silent | 15.3 |

**csharp\_prefer\_braces**

- 如果此规则设置为“true”，则使用大括号为首选项，即使只有一个代码行，也是如此。
- 如果此规则设置为“false”，则不使用大括号为首选项（如允许）。

代码示例：

```csharp
// csharp_prefer_braces = true
if (test) { this.Display(); }

// csharp_prefer_braces = false
if (test) this.Display();
```

.editorconfig 文件示例：

```EditorConfig
# CSharp code style settings:
[*.cs]
csharp_prefer_braces = true:silent
```

## <a name="formatting-conventions"></a>格式设置约定

大部分格式设置约定的规则具有以下格式：

`rule_name = false|true`

可指定“true”（以此样式为首选项）或“false”（不以此样式为首选项）。 不需要指定严重性。 对于一些规则，可指定 true 和 false 以外的其他值来描述应用该规则的时间和位置。

下面的列表显示 Visual Studio 中可用的格式设置约定规则：

- .NET 格式设置
    - [组织 using](#usings)
        - dotnet_sort_system_directives_first
        - dotnet_separate_import_directive_groups
- C# 格式设置
    - [换行符选项](#newline)
        - csharp_new_line_before_open_brace
        - csharp_new_line_before_else
        - csharp_new_line_before_catch
        - csharp_new_line_before_finally
        - csharp_new_line_before_members_in_object_initializers
        - csharp_new_line_before_members_in_anonymous_types
        - csharp_new_line_between_query_expression_clauses
    - [缩进选项](#indent)
        - csharp_indent_case_contents
        - csharp_indent_switch_labels
        - csharp_indent_labels
    - [间距选项](#spacing)
        - csharp_space_after_cast
        - csharp_space_after_keywords_in_control_flow_statements
        - csharp_space_between_method_declaration_parameter_list_parentheses
        - csharp_space_between_method_call_parameter_list_parentheses
        - csharp_space_between_parentheses
        - csharp_space_before_colon_in_inheritance_clause
        - csharp_space_after_colon_in_inheritance_clause
        - csharp_space_around_binary_operators
        - csharp_space_between_method_declaration_empty_parameter_list_parentheses
        - csharp_space_between_method_call_name_and_opening_parenthesis
        - csharp_space_between_method_call_empty_parameter_list_parentheses
    - [换行选项](#wrapping)
        - csharp_preserve_single_line_statements
        - csharp_preserve_single_line_blocks

### <a name="net-formatting-settings"></a>.NET 格式设置

本节中的格式设置规则均适用于 C# 和 Visual Basic。

#### <a name="usings"></a>组织 using

此格式设置规则与相对于其他 using 指令的 System.* using 指令的位置有关。

下表显示规则名称、适用的语言、默认值和第一个支持的 Visual Studio 版本：

| 规则名称 | 适用的语言 | Visual Studio 默认值 | Visual Studio 2017 版本 |
| ----------- | -------------------- | ----------------------| ---------------- |
| dotnet_sort_system_directives_first | C# 和 Visual Basic | true | 15.3 |
| dotnet_separate_import_directive_groups | C# 和 Visual Basic | False | 15.5 |

**dotnet\_sort\_system\_directives_first**

- 如果此规则设置为“true”，则按字母顺序对 System.* using 指令进行排序，并将其放在其他 using 之前。
- 如果此规则设置为“false”，请勿将 System.* using 指令放置在其他 using 指令之前。

代码示例：

```csharp
// dotnet_sort_system_directives_first = true
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;

// dotnet_sort_system_directives_first = false
using System.Collections.Generic;
using Octokit;
using System.Threading.Tasks;
```

.editorconfig 文件示例：

```EditorConfig
# .NET formatting settings:
[*.{cs,vb}]
dotnet_sort_system_directives_first = true
```

dotnet\_separate\_import\_directive\_groups

- 当此规则设置为 true 时，请在 using 指令组之间放置一个空行。
- 当此规则设置为 false 时，请勿在 using 指令组之间放置空行。

代码示例：

```csharp
// dotnet_separate_import_directive_groups = true
using System.Collections.Generic;
using System.Threading.Tasks;

using Octokit;

// dotnet_separate_import_directive_groups = false
using System.Collections.Generic;
using System.Threading.Tasks;
using Octokit;
```

.editorconfig 文件示例：

```EditorConfig
# .NET formatting settings:
[*.{cs,vb}]
dotnet_separate_import_directive_groups = true
```

### <a name="c-formatting-settings"></a>C# 格式设置

本节中的格式设置规则仅适用于 C# 代码。

#### <a name="newline"></a>换行符选项

这些格式设置规则与是否使用新行设置代码的格式有关。

下表显示“新行”规则名称、适用的语言、默认值和第一个支持的 Visual Studio 版本：

| 规则名称 | 适用的语言 | Visual Studio 默认值 | Visual Studio 2017 版本 |
| ----------- | -------------------- | ----------------------| ---------------- |
| csharp_new_line_before_open_brace | C# | 全部 | 15.3 |
| csharp_new_line_before_else | C# | true | 15.3 |
| csharp_new_line_before_catch | C# | true | 15.3 |
| csharp_new_line_before_finally | C# | true | 15.3 |
| csharp_new_line_before_members_in_object_initializers | C# | true | 15.3 |
| csharp_new_line_before_members_in_anonymous_types | C# | true | 15.3 |
| csharp_new_line_between_query_expression_clauses | C# | true | 15.3 |

**csharp\_new\_line\_before\_open_brace**

此规则与左大括号 `{` 应放在前面代码的同一行还是新行上有关。 对于此规则，无需指定“true”或“false”。 改为指定“全部”、“无”或一个或多个码位元素，如方法或属性，从而定义此规则的应用时间。 下表列出了允许值的完整列表：

| 值 | 说明
| ------------- |:-------------|
| accessors, anonymous_methods, anonymous_types, control_blocks, events, indexers, lambdas, local_functions, methods, object_collection_array_initializers, properties, types.<br>（对于多种值，请使用“,”分隔）。 | 需要将大括号置于指定码位元素的新行中（也称为“Allman”样式） |
| 全部 | 对于所有表达式，需要将大括号置于新行（“Allman”样式） |
| 无 | 对于所有表达式，需要将大括号置于同一行（“K&R”） |

代码示例：

```csharp
// csharp_new_line_before_open_brace = all
void MyMethod()
{
    if (...)
    {
        ...
    }
}

// csharp_new_line_before_open_brace = none
void MyMethod() {
    if (...) {
        ...
    }
}
```

**csharp\_new\_line\_before_else**

- 如果此规则设置为“true”，则将 `else` 语句置于新行。
- 如果此规则设置为“false”，则将 `else` 语句置于同一行。

代码示例：

```csharp
// csharp_new_line_before_else = true
if (...) {
    ...
}
else {
    ...
}

// csharp_new_line_before_else = false
if (...) {
    ...
} else {
    ...
}
```

**csharp\_new\_line\_before_catch**

- 如果此规则设置为“true”，则将 `catch` 语句置于新行。
- 如果此规则设置为“false”，则将 `catch` 语句置于同一行。

代码示例：

```csharp
// csharp_new_line_before_catch = true
try {
    ...
}
catch (Exception e) {
    ...
}

// csharp_new_line_before_catch = false
try {
    ...
} catch (Exception e) {
    ...
}
```

**csharp\_new\_line\_before_finally**

- 如果此规则设置为“true”，则需要将 `finally` 语句置于右大括号后的新行。
- 如果此规则设置为“false”，则需要将 `finally` 语句置于右大括号的同一行。

代码示例：

```csharp
// csharp_new_line_before_finally = true
try {
    ...
}
catch (Exception e) {
    ...
}
finally {
    ...
}

// csharp_new_line_before_finally = false
try {
    ...
} catch (Exception e) {
    ...
} finally {
    ...
}
```

**csharp\_new\_line\_before\_members\_in\_object_initializers**

- 如果此规则设置为“true”，对象初始值设定项的成员必须单独占一行。
- 如果此规则设置为“false”，则需要将对象初始值设定项的成员置于同一行。

代码示例：

```csharp
// csharp_new_line_before_members_in_object_initializers = true
var z = new B()
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_object_initializers = false
var z = new B()
{
    A = 3, B = 4
}
```

**csharp\_new\_line\_before\_members\_in\_anonymous_types**

- 如果此规则设置为“true”，则需要将匿名类型的成员置于单独的行。
- 如果此规则设置为“false”，则需要将匿名类型的成员置于同一行。

代码示例：

```csharp
// csharp_new_line_before_members_in_anonymous_types = true
var z = new
{
    A = 3,
    B = 4
}

// csharp_new_line_before_members_in_anonymous_types = false
var z = new
{
    A = 3, B = 4
}
```

**csharp_new_line_between_query_expression_clauses**

- 如果此规则设置为“true”，则需要将查询表达式子句的元素置于单独的行。
- 如果此规则设置为“false”，则需要将查询表达式子句的元素置于同一行。

代码示例：

```csharp
// csharp_new_line_between_query_expression_clauses = true
var q = from a in e
        from b in e
        select a * b;

// csharp_new_line_between_query_expression_clauses = false
var q = from a in e from b in e
        select a * b;
```

.editorconfig 文件示例：

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_new_line_before_open_brace = methods, properties, control_blocks, types
csharp_new_line_before_else = true
csharp_new_line_before_catch = true
csharp_new_line_before_finally = true
csharp_new_line_before_members_in_object_initializers = true
csharp_new_line_before_members_in_anonymous_types = true
csharp_new_line_between_query_expression_clauses = true
```

#### <a name="indent"></a>缩进选项

这些格式设置规则与是否使用缩进设置代码的格式有关。

下表显示规则名称、适用的语言、默认值和第一个支持的 Visual Studio 版本：

| 规则名称 | 适用的语言 | Visual Studio 默认值 | Visual Studio 2017 版本 |
| ----------- | -------------------- | ----------------------| ---------------- |
| csharp_indent_case_contents | C# | true | 15.3 |
| csharp_indent_switch_labels | C# | true | 15.3 |
| csharp_indent_labels | C# | no_change | 15.3 |

**csharp\_indent\_case_contents**

- 如果此规则设置为“true”，则缩进 `switch` 事例内容。
- 如果此规则设置为“false”，则不缩进 `switch` 事例内容。

代码示例：

```csharp
// csharp_indent_case_contents = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_case_contents = false
switch(c) {
    case Color.Red:
    Console.WriteLine("The color is red");
    break;
    case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
    default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

**csharp\_indent\_switch_labels**

- 如果此规则设置为“true”，则缩进 `switch` 标签。
- 如果此规则设置为“false”，则不缩进 `switch` 标签。

代码示例：

```csharp
// csharp_indent_switch_labels = true
switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
}

// csharp_indent_switch_labels = false
switch(c) {
case Color.Red:
    Console.WriteLine("The color is red");
    break;
case Color.Blue:
    Console.WriteLine("The color is blue");
    break;
default:
    Console.WriteLine("The color is unknown.");
    break;
}
```

**csharp\_indent_labels**

此规则不接受“true”或“false”值；此规则接受下表中的值：

| 值 | 说明 |
| ----- |:----------- |
| flush_left | 标签置于最左侧的列 |
| one_less_than_current | 将标签置于比当前上下文少一个缩进的位置 |
| no_change | 将标签置于与当前上下文相同的缩进位置 |

代码示例：

```csharp
// csharp_indent_labels= flush_left
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
error:
        throw new Exception(...);
    }
}

// csharp_indent_labels = one_less_than_current
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
    error:
        throw new Exception(...);
    }
}

// csharp_indent_labels= no_change
class C
{
    private string MyMethod(...)
    {
        if (...) {
            goto error;
        }
        error:
        throw new Exception(...);
    }
}
```

.editorconfig 文件示例：

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_indent_case_contents = true
csharp_indent_switch_labels = true
csharp_indent_labels = flush_left
```

#### <a name="spacing"></a>间距选项

这些格式设置规则与是否使用空格字符设置代码的格式有关。

下表显示规则名称、适用的语言、默认值和第一个支持的 Visual Studio 版本：

| 规则名称 | 适用的语言 | Visual Studio 默认值 | Visual Studio 2017 版本 |
| ----------- | -------------------- | ----------------------| ---------------- |
| csharp_space_after_cast | C# | False | 15.3 |
| csharp_space_after_keywords_in_control_flow_statements | C# | true | 15.3 |
| csharp_space_between_method_declaration_parameter_list_parentheses | C# | False | 15.3 |
| csharp_space_between_method_call_parameter_list_parentheses | C# | False | 15.3 |
| csharp_space_between_parentheses | C# | False | 15.3 |
| csharp_space_before_colon_in_inheritance_clause | C# | true | 15.7 |
| csharp_space_after_colon_in_inheritance_clause | C# | true | 15.7 |
| csharp_space_around_binary_operators | C# | before_and_after | 15.7 |
| csharp_space_between_method_declaration_empty_parameter_list_parentheses | C# | False | 15.7 |
| csharp_space_between_method_call_name_and_opening_parenthesis | C# | False | 15.7 |
| csharp_space_between_method_call_empty_parameter_list_parentheses | C# | False | 15.7 |

**csharp\_space\_after_cast**

- 如果此规则设置为“true”，则转换和值之间需要空格。
- 如果此规则设置为“false”，则转换和值之间不需要空格。

代码示例：

```csharp
// csharp_space_after_cast = true
int y = (int) x;

// csharp_space_after_cast = false
int y = (int)x;
```

**csharp_space_after_keywords_in_control_flow_statements**

- 如果此规则设置为“true”，则在 `for` 循环等控制流语句中，关键字后需要空格。
- 如果此规则设置为“false”，则在 `for` 循环等控制流语句中，关键字后不需要空格。

代码示例：

```csharp
// csharp_space_after_keywords_in_control_flow_statements = true
for (int i;i<x;i++) { ... }

// csharp_space_after_keywords_in_control_flow_statements = false
for(int i;i<x;i++) { ... }
```

**csharp_space_between_method_declaration_parameter_list_parentheses**

- 如果此规则设置为“true”，则在方法声明参数列表的左括号之后和右括号之前放置空格字符。
- 如果此规则设置为“false”，则不要在方法声明参数列表的左括号之后和右括号之前放置空格字符。

代码示例：

```csharp
// csharp_space_between_method_declaration_parameter_list_parentheses = true
void Bark( int x ) { ... }

// csharp_space_between_method_declaration_parameter_list_parentheses = false
void Bark(int x) { ... }
```

**csharp_space_between_method_call_parameter_list_parentheses**

- 如果此规则设置为“true”，则在方法调用的左括号之后和右括号之前放置空格字符。
- 如果此规则设置为“false”，则不要在方法调用的左括号之后和右括号之前放置空格字符。

代码示例：

```csharp
// csharp_space_between_method_call_parameter_list_parentheses = true
MyMethod( argument );

// csharp_space_between_method_call_parameter_list_parentheses = false
MyMethod(argument);
```

**csharp_space_between_parentheses**

此规则接受下表中的一个或多个值：

| 值 | 说明 |
| ----- |:------------|
| control_flow_statements | 在控制流语句的括号之间放置空格 |
| 表达式 | 在表达式的括号之间放置空格 |
| type_casts | 在类型转换中的括号之间放置空格 |

如果省略此规则或使用 `control_flow_statements`、`expressions` 或 `type_casts` 以外的值，则不会应用该设置。

代码示例：

```csharp
// csharp_space_between_parentheses = control_flow_statements
for ( int i = 0; i < 10; i++ ) { }

// csharp_space_between_parentheses = expressions
var z = ( x * y ) - ( ( y - x ) * 3 );

// csharp_space_between_parentheses = type_casts
int y = ( int )x;
```

**csharp\_space\_before\_colon\_in\_inheritance_clause**

- 如果将此规则设置为 true，则类型声明中的基或接口的冒号前需要空格。
- 如果将此规则设置为 false，则类型声明中的基或接口的冒号前不需要空格。

代码示例：

```csharp
// csharp_space_before_colon_in_inheritance_clause = true
interface I
{

}

class C : I
{

}

// csharp_space_before_colon_in_inheritance_clause = false
interface I
{

}

class C: I
{

}
```

**csharp\_space\_after\_colon\_in\_inheritance_clause**

- 如果将此规则设置为 true，则类型声明中的基或接口的冒号后需要空格。
- 如果将此规则设置为 false，则类型声明中的基或接口的冒号后不需要空格。

代码示例：

```csharp
// csharp_space_after_colon_in_inheritance_clause = true
interface I
{

}

class C : I
{

}

// csharp_space_after_colon_in_inheritance_clause = false
interface I
{

}

class C :I
{

}
```

**csharp\_space\_around\_binary_operators**

此规则接受下表中的一个值：

| 值 | 说明 |
| ----- |:------------|
| before_and_after | 在二元运算符前后插入空格 |
| 无 | 删除二元运算符前后的空格 |
| 忽略 | 忽略二元运算符前后的空格 |

如果省略此规则或使用 `before_and_after`、`none` 或 `ignore` 以外的值，则不会应用该设置。

代码示例：

```csharp
// csharp_space_around_binary_operators = before_and_after
return x * (x - y);

// csharp_space_around_binary_operators = none
return x*(x-y);

// csharp_space_around_binary_operators = ignore
return x  *  (x-y);
```

**csharp_space_between_method_declaration_empty_parameter_list_parentheses**

- 如果将此规则设置为 true，则在方法声明的空参数列表括号内插入空格。
- 如果将此规则设置为 false，则删除方法声明的空参数列表括号内的空格。

代码示例：

```csharp
// csharp_space_between_method_declaration_empty_parameter_list_parentheses = true
void Goo( )
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}

// csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

**csharp_space_between_method_call_name_and_opening_parenthesis**

- 如果将此规则设置为 true，则在方法调用名称和左括号之间插入空格。
- 如果将此规则设置为 false，则删除方法调用名称和左括号之间的空格。

代码示例：

```csharp
// csharp_space_between_method_call_name_and_opening_parenthesis = true
void Goo()
{
    Goo (1);
}

void Goo(int x)
{
    Goo ();
}

// csharp_space_between_method_call_name_and_opening_parenthesis = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

**csharp_space_between_method_call_empty_parameter_list_parentheses**

- 如果将此规则设置为 true，则在空参数列表括号内插入空格。
- 如果将此规则设置为 false，则删除空参数列表括号内的空格。

代码示例：

```csharp
// csharp_space_between_method_call_empty_parameter_list_parentheses = true
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo( );
}

// csharp_space_between_method_call_empty_parameter_list_parentheses = false
void Goo()
{
    Goo(1);
}

void Goo(int x)
{
    Goo();
}
```

.editorconfig 文件示例：

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_space_after_cast = true
csharp_space_after_keywords_in_control_flow_statements = true
csharp_space_between_method_declaration_parameter_list_parentheses = true
csharp_space_between_method_call_parameter_list_parentheses = true
csharp_space_between_parentheses = control_flow_statements, type_casts
csharp_space_before_colon_in_inheritance_clause = true
csharp_space_after_colon_in_inheritance_clause = true
csharp_space_around_binary_operators = before_and_after
csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
csharp_space_between_method_call_name_and_opening_parenthesis = false
csharp_space_between_method_call_empty_parameter_list_parentheses = false
```

#### <a name="wrapping"></a>换行选项

这些格式设置规则与语句和代码块中单一行以及单独的行的使用有关。

下表显示规则名称、适用的语言、默认值和第一个支持的 Visual Studio 版本：

| 规则名称 | 适用的语言 | Visual Studio 默认值 | Visual Studio 2017 版本 |
| ----------- | -------------------- | ----------------------| ---------------- |
| csharp_preserve_single_line_statements | C# | true | 15.3 |
| csharp_preserve_single_line_blocks | C# | true | 15.3 |

**csharp_preserve_single_line_statements**

- 如果此规则设置为“true”，则将语句和成员声明保留在同一行上。
- 如果此规则设置为“false”，则将语句和成员声明保留在不同的行上。

代码示例：

```csharp
//csharp_preserve_single_line_statements = true
int i = 0; string name = "John";

//csharp_preserve_single_line_statements = false
int i = 0;
string name = "John";
```

**csharp_preserve_single_line_blocks**

- 如果此规则设置为“true”，则将代码块保留在单一的行上。
- 如果此规则设置为“false”，则将代码块保留在单独的行上。

代码示例：

```csharp
//csharp_preserve_single_line_blocks = true
public int Foo { get; set; }

//csharp_preserve_single_line_blocks = false
public int MyProperty
{
    get; set;
}
```

.editorconfig 文件示例：

```EditorConfig
# CSharp formatting settings:
[*.cs]
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true
```

## <a name="example-editorconfig-file"></a>EditorConfig 文件示例

下面是具有默认选项的示例 .editorconfig 文件，可帮助你入门：

```EditorConfig
###############################
# Core EditorConfig Options   #
###############################

root = true

# All files
[*]
indent_style = space

# Code files
[*.{cs,csx,vb,vbx}]
indent_size = 4
insert_final_newline = true
charset = utf-8-bom

###############################
# .NET Coding Conventions     #
###############################

[*.{cs,vb}]
# Organize usings
dotnet_sort_system_directives_first = true
dotnet_separate_import_directive_groups = false

# this. preferences
dotnet_style_qualification_for_field = false:silent
dotnet_style_qualification_for_property = false:silent
dotnet_style_qualification_for_method = false:silent
dotnet_style_qualification_for_event = false:silent

# Language keywords vs BCL types preferences
dotnet_style_predefined_type_for_locals_parameters_members = true:silent
dotnet_style_predefined_type_for_member_access = true:silent

# Parentheses preferences
dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_other_binary_operators = always_for_clarity:silent
dotnet_style_parentheses_in_other_operators = never_if_unnecessary:silent

# Modifier preferences
dotnet_style_require_accessibility_modifiers = for_non_interface_members:silent
dotnet_style_readonly_field = true:suggestion

# Expression-level preferences
dotnet_style_object_initializer = true:suggestion
dotnet_style_collection_initializer = true:suggestion
dotnet_style_explicit_tuple_names = true:suggestion
dotnet_style_null_propagation = true:suggestion
dotnet_style_coalesce_expression = true:suggestion
dotnet_style_prefer_is_null_check_over_reference_equality_method = true:silent
dotnet_style_prefer_inferred_tuple_names = true:suggestion
dotnet_style_prefer_inferred_anonymous_type_member_names = true:suggestion
dotnet_style_prefer_auto_properties = true:silent
dotnet_style_prefer_conditional_expression_over_assignment = true:silent
dotnet_style_prefer_conditional_expression_over_return = true:silent

###############################
# Naming Conventions          #
###############################

# Style Definitions
dotnet_naming_style.pascal_case_style.capitalization             = pascal_case

# Use PascalCase for constant fields
dotnet_naming_rule.constant_fields_should_be_pascal_case.severity = suggestion
dotnet_naming_rule.constant_fields_should_be_pascal_case.symbols  = constant_fields
dotnet_naming_rule.constant_fields_should_be_pascal_case.style    = pascal_case_style
dotnet_naming_symbols.constant_fields.applicable_kinds            = field
dotnet_naming_symbols.constant_fields.applicable_accessibilities  = *
dotnet_naming_symbols.constant_fields.required_modifiers          = const

###############################
# C# Code Style Rules         #
###############################

[*.cs]
# var preferences
csharp_style_var_for_built_in_types = true:silent
csharp_style_var_when_type_is_apparent = true:silent
csharp_style_var_elsewhere = true:silent

# Expression-bodied members
csharp_style_expression_bodied_methods = false:silent
csharp_style_expression_bodied_constructors = false:silent
csharp_style_expression_bodied_operators = false:silent
csharp_style_expression_bodied_properties = true:silent
csharp_style_expression_bodied_indexers = true:silent
csharp_style_expression_bodied_accessors = true:silent

# Pattern-matching preferences
csharp_style_pattern_matching_over_is_with_cast_check = true:suggestion
csharp_style_pattern_matching_over_as_with_null_check = true:suggestion

# Null-checking preferences
csharp_style_throw_expression = true:suggestion
csharp_style_conditional_delegate_call = true:suggestion

# Modifier preferences
csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async:suggestion

# Expression-level preferences
csharp_prefer_braces = true:silent
csharp_style_deconstructed_variable_declaration = true:suggestion
csharp_prefer_simple_default_expression = true:suggestion
csharp_style_pattern_local_over_anonymous_function = true:suggestion
csharp_style_inlined_variable_declaration = true:suggestion

###############################
# C# Formatting Rules         #
###############################

# New line preferences
csharp_new_line_before_open_brace = all
csharp_new_line_before_else = true
csharp_new_line_before_catch = true
csharp_new_line_before_finally = true
csharp_new_line_before_members_in_object_initializers = true
csharp_new_line_before_members_in_anonymous_types = true
csharp_new_line_between_query_expression_clauses = true

# Indentation preferences
csharp_indent_case_contents = true
csharp_indent_switch_labels = true
csharp_indent_labels = flush_left

# Space preferences
csharp_space_after_cast = false
csharp_space_after_keywords_in_control_flow_statements = true
csharp_space_between_method_call_parameter_list_parentheses = false
csharp_space_between_method_declaration_parameter_list_parentheses = false
csharp_space_between_parentheses = false
csharp_space_before_colon_in_inheritance_clause = true
csharp_space_after_colon_in_inheritance_clause = true
csharp_space_around_binary_operators = before_and_after
csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
csharp_space_between_method_call_name_and_opening_parenthesis = false
csharp_space_between_method_call_empty_parameter_list_parentheses = false

# Wrapping preferences
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true

##################################
# Visual Basic Code Style Rules  #
##################################

[*.vb]
# Modifier preferences
visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async:suggestion
```

## <a name="see-also"></a>请参阅

- [快速操作](../ide/quick-actions.md)
- [EditorConfig 适用的 .NET 命名约定](../ide/editorconfig-naming-conventions.md)
- [创建可移植的自定义编辑器选项](../ide/create-portable-custom-editor-options.md)
- [.NET 编译器平台的 .editorconfig 文件](https://github.com/dotnet/roslyn/blob/master/.editorconfig)
