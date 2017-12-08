---
title: "EditorConfig 的 .NET 编码约定设置 | Microsoft Docs"
ms.custom: 
ms.date: 10/13/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
helpviewer_keywords: editor
ms.assetid: 
caps.latest.revision: "1"
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.technology: vs-ide-general
ms.openlocfilehash: f59065777de938c07a88d722cabdba82d6b19c02
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2017
---
# <a name="net-coding-convention-settings-for-editorconfig"></a>EditorConfig 的 .NET 编码约定设置
通过使用 [EditorConfig](https://docs.microsoft.com/en-us/visualstudio/ide/create-portable-custom-editor-options) 文件，可在基本代码中定义和维护一致的代码样式。 EditorConfig 包括多个核心格式设置属性，如 `indent_style` 和 `indent_size`。 在 Visual Studio 中，还可使用 EditorConfig 文件配置 .NET 编码约定设置。 通过 EditorConfig 文件，可以启用或禁用单个 .NET 编码约定，并可通过严重级别配置强制实施约定的程度。 若要深入了解如何使用 EditorConfig 强制实施基本代码一致性，请参阅[创建可移植的自定义编辑器设置](https://docs.microsoft.com/en-us/visualstudio/ide/create-portable-custom-editor-options)。 还可将 [.NET 编译器平台的 .editorconfig 文件](https://github.com/dotnet/roslyn/blob/master/.editorconfig)视作示例。  

有三种受支持的 .NET 编码约定类别：  
- [语言约定](#language-conventions)  
   与 C# 或 Visual Basic 语言相关的规则。 例如，定义变量或首选 expression-bodied 成员时，可以指定与 `var` 或显式类型的使用相关的规则。  
- [格式设置约定](#formatting-conventions)  
   与代码的布局和结构有关的规则，其作用是使代码更易于阅读。 例如，可以指定控制块中的 Allman 大括号或首选空格的相关规则。  
- [命名约定](#naming-conventions)  
   与码位元素的命名有关的规则。 例如，可以指定 `async` 方法必须以“Async”结尾。  

## <a name="language-conventions"></a>语言约定  
语言约定的规则具有以下格式：  

`options_name = false|true : none|suggestion|warning|error`  

对于每个语言约定规则，必须指定“true”（以此样式为首选项）或“false”（不以此样式为首选项），以及“严重性”。 “严重性”指定强制执行该样式的级别。  

下表列出了可能的严重性值及其效果：  

严重性 | 效果
:------- | ------
无或无提示 | 如违反此规则，不会向用户显示任何内容。 但代码生成功能会以此样式生成代码。  
建议 | 如违反此样式规则，会将其作为建议向用户显示。 建议显示为前两个字符下的三个灰点。  
警告 | 如违反此样式规则，显示编译器警告。  
错误 | 如违反此样式规则，显示编译器错误。  

以下列表显示允许的语言约定规则：  

- .NET 代码样式设置
    - [“This.”和“Me.”限定符](#this_and_me)
        - dotnet\_style\_qualification\_for_field
        - dotnet\_style\_qualification\_for_property
        - dotnet\_style\_qualification\_for_method
        - dotnet\_style\_qualification\_for_event
    - [语言关键字，而非类型引用的框架类型名称](#language_keywords)
        - dotnet\_style\_predefined\_type\_for\_locals\_parameters_members
        - dotnet\_style\_predefined\_type\_for\_member_access
    - [表达式级首选项](#expression_level)
        - dotnet\_style\_object_initializer
        - dotnet\_style\_collection_initializer
        - dotnet\_style\_explicit\_tuple_names
        - dotnet\_style\_coalesce_expression
        - dotnet\_style\_null_propagation
- C# 代码样式设置
    - [隐式和显式类型](#var)
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
    - [“NULL”检查首选项](#null_checking)
        - csharp\_style\_throw_expression
        - csharp\_style\_conditional\_delegate_call
    - [代码块首选项](#code_block)
        - csharp\_prefer_braces

### <a name="net-code-style-settings"></a>.NET 代码样式设置  
本节中的样式规则均适用于 C# 和 Visual Basic。 若要查看以首选编程语言编写的代码示例，请在浏览器窗口右上角的下拉“语言”菜单中选择它。  

#### <a name="this_and_me">“This.”和“Me.”限定符</a>
此样式规则（规则 ID IDE0003 和 IDE0009）可应用于字段、属性、方法或事件。 值为“true”表示代码符号以 `this.` (C#) 或 `Me.` (Visual Basic) 开头为首选项。 值为“false”表示码位元素不以 `this.` 或 `Me.` 开头为首选项。  

下表显示规则名称、适用的编程语言、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| ----------- | -------------------- | ----------------------| ----------------  |
| dotnet_style_qualification_for_field | C# 和 Visual Basic | false:none | Visual Studio 2017 RTW |
| dotnet_style_qualification_for_property | C# 和 Visual Basic | false:none | Visual Studio 2017 RTW |
| dotnet_style_qualification_for_method | C# 和 Visual Basic | false:none | Visual Studio 2017 RTW |
| dotnet_style_qualification_for_event | C# 和 Visual Basic | false:none | Visual Studio 2017 RTW |   

**dotnet\_style\_qualification\_for_field**  
如果此规则设置为“true”，则字段以 `this.` (C#) 或 `Me.` (Visual Basic) 开头为首选项。  
如果此规则设置为“false”，则字段不以 `this.` 或 `Me.` 开头为首选项。  

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
如果此规则设置为“true”，则属性以 `this.` (C#) 或 `Me.` (Visual Basic) 开头为首选项。  
如果此规则设置为“false”，则属性不以 `this.` 或 `Me.` 开头为首选项。  

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
如果此规则设置为“true”，则方法以 `this.` (C#) 或 `Me.` (Visual Basic) 开头为首选项。  
如果此规则设置为“false”，则方法不以 `this.` 或 `Me.` 开头为首选项。  

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
如果此规则设置为“true”，则事件以 `this.` (C#) 或 `Me.` (Visual Basic) 开头为首选项。  
如果此规则设置为“false”，则事件不以 `this.` 或 `Me.` 开头为首选项。  

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

```
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_qualification_for_field = false:suggestion
dotnet_style_qualification_for_property = false:suggestion
dotnet_style_qualification_for_method = false:suggestion
dotnet_style_qualification_for_event = false:suggestion
```

#### <a name="language_keywords">语言关键字，而非类型引用的框架类型名称</a>
此样式规则可应用到本地变量、方法参数和类成员，也可作为针对类型成员访问表达式的单独规则。 值为“true”代表对于类型（其中具有用于表示该类型的关键字），语言关键字（例如 `int` 或 `Integer`）为首选项，而非类型名称（例如 `Int32`）。 值为“false”代表类型名称为首选项，而非语言关键字。  

下表显示规则名称、规则 ID、适用的编程语言、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| dotnet_style_predefined_type_for_locals_parameters_members | IDE0012 和 IDE0014 | C# 和 Visual Basic | true:none | Visual Studio 2017 RTW |
| dotnet_style_predefined_type_for_member_access | IDE0013 和 IDE0015 | C# 和 Visual Basic | true:none | Visual Studio 2017 RTW |  

**dotnet\_style\_predefined\_type\_for\_locals\_parameters_members**  
如果此规则设置为“true”，则对于类型（其中具有用于表示该类型的关键字），本地变量、方法参数和类成员的语言关键字为首选项，而非类型名称。  
如果此规则设置为“false”，则本地变量、方法参数和类成员的类型名称为首选项，而非语言关键字。  

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
如果此规则设置为“true”，则对于类型（其中具有用于表示该类型的关键字），成员访问表达式的语言关键字为首选项，而非类型名称。  
如果此规则设置为“false”，则成员访问表达式的类型名称为首选项，而非语言关键字。  

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

```
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_predefined_type_for_locals_parameters_members = true:suggestion
dotnet_style_predefined_type_for_member_access = true:suggestion
``` 

#### <a name="expression_level">表达式级首选项</a>  
本节中的样式规则与表达式级别首选项有关，包括对象初始值设定项、集合初始值设定项、显式元组名称、NULL 合并表达式与三元运算符、NULL 条件运算符的使用。  

下表显示规则名称、规则 ID、适用的编程语言、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| dotnet_style_object_initializer | IDE0017 | C# 和 Visual Basic | true:suggestion | Visual Studio 2017 RTW |
| dotnet_style_collection_initializer | IDE0028 | C# 和 Visual Basic | true:suggestion | Visual Studio 2017 RTW |
| dotnet_style_explicit_tuple_names | IDE0033 | C# 7.0+ 和 Visual Basic 15+ | true:suggestion | Visual Studio 2017 RTW |
| dotnet_style_coalesce_expression | IDE0029 | C# 和 Visual Basic | true:suggestion | Visual Studio 2017 RTW |
| dotnet_style_null_propagation | IDE0031 | C# 6.0+ 和 Visual Basic 14+ | true:suggestion | Visual Studio 2017 RTW | 

**dotnet\_style\_object_initializer**  
如果此规则设置为“true”，则使用对象初始值设定项来初始化对象为首选项（如可能）。  
如果此规则设置为“false”，则不使用对象初始值设定项来初始化对象为首选项。  

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
如果此规则设置为“true”，则使用集合初始值设定项来初始化集合为首选项（如可能）。  
如果此规则设置为“false”，则不使用集合初始值设定项来初始化集合为首选项。

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
如果此规则设置为“true”，则元组名称为首选项，而非 ItemX 属性。  
如果此规则设置为“false”，则 ItemX 属性为首选项，而非元组名称。  

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

**dotnet\_style\_coalesce_expression**  
如果此规则设置为“true”，则 NULL 合并表达式为首选项，而非三元运算符检查。  
如果此规则设置为“false”，则三元运算符检查为首选项，而非 NULL 合并表达式。

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
如果此规则设置为“true”，则使用 NULL 条件运算符（若可能）为首选项。  
如果此规则设置为“false”，则使用三元 NULL 检查（若可能）为首选项。  

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

```
# CSharp and Visual Basic code style settings:
[*.{cs,vb}]
dotnet_style_object_initializer = true:suggestion
dotnet_style_collection_initializer = true:suggestion
dotnet_style_explicit_tuple_names = true:suggestion
dotnet_style_coalesce_expression = true:suggestion
dotnet_style_null_propagation = true:suggestion
``` 

### <a name="c-code-style-settings"></a>C# 代码样式设置  
本节中的样式规则仅适用于 C#。  

#### <a name="var">隐式和显式类型</a>
本节中的样式规则（规则 ID 为 IDE0007 和 IDE0008）与变量声明中的 [var](/dotnet/csharp/language-reference/keywords/var) 关键字和显式类型的使用有关。 此规则可单独应用于内置类型（前提是该类型为明显）和其他情况。  

下表显示规则名称、适用的编程语言、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_style_var_for_built_in_types | C# | true:none | Visual Studio 2017 RTW |
| csharp_style_var_when_type_is_apparent | C# | true:none | Visual Studio 2017 RTW |
| csharp_style_var_elsewhere | C# | true:none | Visual Studio 2017 RTW |

**csharp\_style\_var\_for\_built\_in_types**  
如果此规则设置为“true”，则使用 `var` 声明 `int` 等内置系统类型的变量为首选项。  
如果此规则设置为“false”，则使用显示类型声明 `int` 等内置系统类型的变量为首选项，而非使用 `var`。

代码示例：  

```csharp
// csharp_style_var_for_built_in_types = true
var x = 5;

// csharp_style_var_for_built_in_types = false
int x = 5;
```

**csharp\_style\_var\_when\_type\_is_apparent**  
如果此规则设置为“true”，则声明表达式右侧已提到该类型时，使用 `var` 为首选项。  
如果此规则设置为“false”，则声明表达式右侧已提到该类型时，使用显式类型为首选项，而非 `var`。  

代码示例：  

```csharp
// csharp_style_var_when_type_is_apparent = true
var obj = new Customer();

// csharp_style_var_when_type_is_apparent = false
Customer obj = new Customer();
```

**csharp\_style\_var_elsewhere**  
如果此规则设置为“true”，则在任何情况下，`var` 为首选项，而非显式类型，除非由另一个代码样式规则替代。  
如果此规则设置为“false”，则在任何情况下，显式类型为首选项，而非 `var`，除非由另一个代码样式规则替代。  

代码示例：  

```csharp
// csharp_style_var_elsewhere = true
var f = this.Init();

// csharp_style_var_elsewhere = false
bool f = this.Init();
```

示例 .editorconfig 文件：  

```
# CSharp code style settings:
[*.cs]
csharp_style_var_for_built_in_types = true:suggestion
csharp_style_var_when_type_is_apparent = true:suggestion
csharp_style_var_elsewhere = true:suggestion
``` 

#### <a name="expression_bodied_members">Expression-Bodied 成员</a>
本节中的样式规则与在逻辑由单个表达式组成的情况下，[expression-bodied 成员](/dotnet/csharp/programming-guide/statements-expressions-operators/expression-bodied-members)的使用有关。 此规则可应用于方法、构造函数、运算符、属性、索引器和访问器。  

下表显示规则名称、规则 ID、适用的语言版本、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| csharp_style_expression_bodied_methods | IDE0022 | C# 6.0+ | false:none | Visual Studio 2017 RTW |
| csharp_style_expression_bodied_constructors | IDE0021 | C# 7.0+ | false:none | Visual Studio 2017 RTW |
| csharp_style_expression_bodied_operators | IDE0023 和 IDE0024 | C# 7.0+ | false:none | Visual Studio 2017 RTW |
| csharp_style_expression_bodied_properties | IDE0025 | C# 7.0+ | true:none | Visual Studio 2017 RTW |
| csharp_style_expression_bodied_indexers | IDE0026 | C# 7.0+ | true:none | Visual Studio 2017 RTW |
| csharp_style_expression_bodied_accessors | IDE0027 | C# 7.0+ | true:none | Visual Studio 2017 RTW |  

**csharp\_style\_expression\_bodied_methods**  
如果此规则设置为“true”，则方法的 expression-bodied 成员为首选项。  
如果此规则设置为“false”，则方法的 expression-bodied 成员不是首选项。  

代码示例：  

```csharp
// csharp_style_expression_bodied_methods = true
public int GetAge() => this.Age;

// csharp_style_expression_bodied_methods = false
public int GetAge() { return this.Age; }
```  

**csharp\_style\_expression\_bodied_constructors**  
如果此规则设置为“true”，则构造函数的 expression-bodied 成员为首选项。  
如果此规则设置为“false”，则构造函数的 expression-bodied 成员不是首选项。  

代码示例：  

```csharp
// csharp_style_expression_bodied_constructors = true
public Customer(int age) => Age = age;

// csharp_style_expression_bodied_constructors = false
public Customer(int age) { Age = age; }
```  

**csharp\_style\_expression\_bodied_operators**  
如果此规则设置为“true”，则运算符的 expression-bodied 成员为首选项。  
如果此规则设置为“false”，则运算符的 expression-bodied 成员不是首选项。  

代码示例：  

```csharp
// csharp_style_expression_bodied_operators = true
public static ComplexNumber operator +(ComplexNumber c1, ComplexNumber c2)
    => new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary);

// csharp_style_expression_bodied_operators = false
public static ComplexNumber operator +(ComplexNumber c1, ComplexNumber c2)
{ return new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary); }
```  

**csharp\_style\_expression\_bodied_properties**  
如果此规则设置为“true”，则属性的 expression-bodied 成员为首选项。  
如果此规则设置为“false”，则属性的 expression-bodied 成员不是首选项。  

代码示例：  

```csharp
// csharp_style_expression_bodied_properties = true
public int Age => _age;

// csharp_style_expression_bodied_properties = false
public int Age { get { return _age; }}
```  

**csharp\_style\_expression\_bodied_indexers**  
如果此规则设置为“true”，则索引器的 expression-bodied 成员为首选项。  
如果此规则设置为“false”，则索引器的 expression-bodied 成员不是首选项。  

代码示例：  

```csharp
// csharp_style_expression_bodied_indexers = true
public T this[int i] => _value[i];

// csharp_style_expression_bodied_indexers = false
public T this[int i] { get { return _values[i]; } }
```  

**csharp\_style\_expression\_bodied_accessors**  
如果此规则设置为“true”，则访问器的 expression-bodied 成员为首选项。  
如果此规则设置为“false”，则访问器的 expression-bodied 成员不是首选项。  

代码示例：  

```csharp
// csharp_style_expression_bodied_accessors = true
public int Age { get => _age; set => _age = value; }

// csharp_style_expression_bodied_accessors = false
public int Age { get { return _age; } set { _age = value; } }
```  

示例 .editorconfig 文件：  

```
# CSharp code style settings:
[*.cs]
csharp_style_expression_bodied_methods = false:none
csharp_style_expression_bodied_constructors = false:none
csharp_style_expression_bodied_operators = false:none
csharp_style_expression_bodied_properties = true:none
csharp_style_expression_bodied_indexers = false:none
csharp_style_expression_bodied_accessors = false:none
```  

#### <a name="pattern_matching">模式匹配</a>
本节中的样式规则与 C# 中[模式匹配](/dotnet/csharp/pattern-matching)的使用有关。  

下表显示规则名称、规则 ID、适用的语言版本、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| csharp_style_pattern_matching_over_is_with_cast_check | IDE0020 | C# 7.0+ | true:suggestion | Visual Studio 2017 RTW |
| csharp_style_pattern_matching_over_as_with_null_check | IDE0019 | C# 7.0+ | true:suggestion | Visual Studio 2017 RTW |

**csharp\_style\_pattern\_matching\_over\_is\_with\_cast_check**  
如果此规则设置为“true”，则模式匹配为首选项，而非带类型强制转换的 `is` 表达式。  
如果此规则设置为“false”，则带类型强制转换的 `is` 表达式为首选项，而非模式匹配。  

代码示例：  

```csharp
// csharp_style_pattern_matching_over_is_with_cast_check = true
if (o is int i) {...}

// csharp_style_pattern_matching_over_is_with_cast_check = false
if (o is int) {var i = (int)o; ... }
```

**csharp\_style\_pattern\_matching\_over\_as\_with\_null_check**  
如果此规则设置为“true”，则使用模式匹配确定内容是否为某个特定类型为首选项，而非使用带 NULL 检查的 `as` 表达式。  
如果此规则设置为“false”，则使用带 NULL 检查的 `as` 表达式确定内容是否为某个特定类型为首选项，而非使用模式匹配。  

代码示例：  

```csharp
// csharp_style_pattern_matching_over_as_with_null_check = true
if (o is string s) {...}

// csharp_style_pattern_matching_over_as_with_null_check = false
var s = o as string;
if (s != null) {...}
```

示例 .editorconfig 文件：  

```
# CSharp code style settings:
[*.cs]
csharp_style_pattern_matching_over_is_with_cast_check = true:suggestion
csharp_style_pattern_matching_over_as_with_null_check = true:suggestion
```

#### <a name="inlined_variable_declarations">内联变量声明</a>
此样式规则与 `out` 变量是否声明为内联有关。 从 C# 7 开始，可以[在方法调用的实际参数列表中声明 out 变量](/dotnet/csharp/language-reference/keywords/out-parameter-modifier#calling-a-method-with-an-out-argument)，而不是在单独的变量声明中。  

下表显示规则名称、规则 ID、适用的语言版本、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| --------- | -------- | -------------------- | ----------------------| ----------------  |
| csharp_style_inlined_variable_declaration | IDE0018 | C# 7.0+ | true:suggestion | Visual Studio 2017 RTW |

**csharp\_style\_inlined\_variable_declaration**  
如果此规则设置为“true”，则 `out` 变量在方法调用的参数列表中声明为内联为首选项（如可能）。  
如果此规则设置为“false”，则在方法调用之前声明 `out` 变量为首选项。  

代码示例：  

```csharp
// csharp_style_inlined_variable_declaration = true
if (int.TryParse(value, out int i) {...}

// csharp_style_inlined_variable_declaration = fale
int i;
if (int.TryParse(value, out i) {...}
```

示例 .editorconfig 文件：  

```
# CSharp code style settings:
[*.cs]
csharp_style_inlined_variable_declaration = true:suggestion
```

#### <a name="expression_level_csharp">表达式级首选项</a>
此样式规则与在编译器可以推断表达式类型的情况下，[默认值表达式的 `default` 文本](/dotnet/csharp/programming-guide/statements-expressions-operators/default-value-expressions#default-literal-and-type-inference)的使用有关。  

下表显示规则名称、规则 ID、适用的语言版本、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| csharp_prefer_simple_default_expression | IDE0034 | C# 7.1+ | true:suggestion | Visual Studio 2017 v. 15.3 |

**csharp\_prefer\_simple\_default_expression**  
如果此规则设置为“true”，则 `default` 为首选项，而非 `default(T)`。  
如果此规则设置为“false”，则 `default(T)` 为首选项，而非 `default`。  

代码示例：  

```csharp 
// csharp_prefer_simple_default_expression = true
void DoWork(CancellationToken cancellationToken = default) { ... }

// csharp_prefer_simple_default_expression = false
void DoWork(CancellationToken cancellationToken = default(CancellationToken)) { ... }
```

示例 .editorconfig 文件：  

```
# CSharp code style settings:
[*.cs]
csharp_prefer_simple_default_expression = true:suggestion
``` 

#### <a name="null_checking">“NULL”检查首选项</a>
这些样式规则与 `null` 检查的相关语法有关，包括 `throw` 表达式或 `throw` 语句的使用，以及调用 [lambda 表达式](/dotnet/csharp/lambda-expressions)时是否执行 NULL 检查或使用条件合并运算符 (`?.`)。  

下表显示规则名称、规则 ID、适用的语言版本、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| csharp_style_throw_expression | IDE0016 | C# 7.0+ | true:suggestion | Visual Studio 2017 RTW |
| csharp_style_conditional_delegate_call | IDE0041 | C# 6.0+ | true:suggestion | Visual Studio 2017 RTW |

**csharp\_style\_throw_expression**  
如果此规则设置为“true”，则使用 `throw` 表达式为首选项，而非使用 `throw` 语句。  
如果此规则设置为“false”，则使用 `throw` 语句为首选项，而非使用 `throw` 表达式。  

代码示例：  

```csharp
// csharp_style_throw_expression = true
this.s = s ?? throw new ArgumentNullException(nameof(s));

// csharp_style_throw_expression = false
if (s == null) { throw new ArgumentNullException(nameof(s)); }
this.s = s;
```

**csharp\_style\_conditional\_delegate_call**   
如果此规则设置为“true”，则在调用 Lambda 表达式时使用条件合并运算符 (`?.`) 为首选项，而非执行 NULL 检查。  
如果此规则设置为“false”，则在调用 Lambda 表达式之前执行 NULL 检查为首选项，而非使用条件合并运算符 (`?.`)。  

代码示例：  

```csharp
// csharp_style_conditional_delegate_call = true
func?.Invoke(args);

// csharp_style_conditional_delegate_call = false
if (func != null) { func(args); }
```

示例 .editorconfig 文件：  

```
# CSharp code style settings:
[*.cs]
csharp_style_throw_expression = true:suggestions:
csharp_style_conditional_delegate_call = false:suggestion
```

#### <a name="code_block">代码块首选项</a>
此样式规则与是否使用大括号 `{ }` 将代码块括起来有关。  

下表显示规则名称、规则 ID、适用的语言版本、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 规则 ID | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| --------- | ------- | -------------------- | ----------------------| ----------------  |
| csharp_prefer_braces | IDE0011 | C# | true:none | Visual Studio 2017 v. 15.3 |

**csharp\_prefer\_braces**   
如果此规则设置为“true”，则使用大括号为首选项，即使只有一个代码行，也是如此。  
如果此规则设置为“false”，则不使用大括号为首选项（如允许）。  

代码示例：  

```csharp
// csharp_prefer_braces = true
if (test) { this.Display(); }

// csharp_prefer_braces = false
if (test) this.Display();
```

示例 .editorconfig 文件：  

```
# CSharp code style settings:
[*.cs]
csharp_prefer_braces = true:none
```

## <a name="formatting-conventions"></a>格式设置约定
大部分格式设置约定的规则具有以下格式：  

`rule_name = false|true`  

可指定“true”（以此样式为首选项）或“false”（不以此样式为首选项）。 不需要指定严重性。 对于一些规则，可指定 true 和 false 以外的其他值来描述应用该规则的时间和位置。  

下面的列表显示 Visual Studio 中可用的格式设置约定规则：  

- .NET 格式设置
    - [组织 Using](#usings)
        - dotnet_sort_system_directives_first
- C# 格式设置
    - [新建行选项](#newline)
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
    - [换行选项](#wrapping)
        - csharp_preserve_single_line_statements
        - csharp_preserve_single_line_blocks

### <a name="net-formatting-settings"></a>.NET 格式设置
本节中的格式设置规则均适用于 C# 和 Visual Basic。  

#### <a name="usings">组织 using</a>
此格式设置规则与相对于其他 using 指令的 System.* using 指令的位置有关。  

下表显示规则名称、适用的语言、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| ----------- | -------------------- | ----------------------| ----------------  |
| dotnet_sort_system_directives_first |  C# 和 Visual Basic | true | Visual Studio 2017 v. 15.3  |

**dotnet\_sort\_system\_directives_first**  
如果此规则设置为“true”，则按字母顺序对 System.* using 指令进行排序，并将其放在其他 using 之前。  
如果此规则设置为“false”，请勿将 System.* using 指令放置在其他 using 指令之前。  

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

示例 .editorconfig 文件：  

```
# .NET formatting settings:
[*.{cs,vb}]
dotnet_sort_system_directives_first = true
``` 

### <a name="csharp_formatting">C# 格式设置</a>  
本节中的格式设置规则仅适用于 C# 代码。  

#### <a name="newline">新建行选项</a>  
这些格式设置规则与是否使用新行设置代码的格式有关。  

下表显示“新行”规则名称、适用的语言、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_new_line_before_open_brace |  C# | 全部 | Visual Studio 2017 v. 15.3  |
| csharp_new_line_before_else |  C# | true | Visual Studio 2017 v. 15.3  |
| csharp_new_line_before_catch |  C# | true | Visual Studio 2017 v. 15.3  |
| csharp_new_line_before_finally |  C# | true | Visual Studio 2017 v. 15.3  |
| csharp_new_line_before_members_in_object_initializers |  C# | true | Visual Studio 2017 v. 15.3  |
| csharp_new_line_before_members_in_anonymous_types |  C# | true | Visual Studio 2017 v. 15.3  |
| csharp_new_line_between_query_expression_clauses |  C# | true | Visual Studio 2017 v. 15.3  |

**csharp\_new\_line\_before\_open_brace**  
此规则与左大括号 `{` 应放在前面代码的同一行还是新行上有关。 对于此规则，无需指定“true”或“false”。 改为指定“全部”、“无”或一个或多个码位元素，如方法或属性，从而定义此规则的应用时间。 下表列出了允许值的完整列表：  

| 值 | 描述 
| ------------- |:-------------|
| accessors、anonymous_methods、anonymous_types、control_blocks、events, indexers、lambdas、local_functions、methods、object_collection、properties、types。<br>（对于多种值，请使用“,”分隔）。 | 需要将大括号置于指定码位元素的新行中（也称为“Allman”样式） |
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
如果此规则设置为“true”，则将 `else` 语句置于新行。  
如果此规则设置为“false”，则将 `else` 语句置于同一行。  

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
如果此规则设置为“true”，则将 `catch` 语句置于新行。  
如果此规则设置为“false”，则将 `catch` 语句置于同一行。  

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
如果此规则设置为“true”，则需要将 `finally` 语句置于右大括号后的新行。  
如果此规则设置为“false”，则需要将 `finally` 语句置于右大括号的同一行。  

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
如果此规则设置为“true”，则需要将对象初始值设定项的成员置于单独的行。  
如果此规则设置为“false”，则需要将对象初始值设定项的成员置于同一行。  

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
如果此规则设置为“true”，则需要将匿名类型的成员置于单独的行。  
如果此规则设置为“false”，则需要将匿名类型的成员置于同一行。  

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
如果此规则设置为“true”，则需要将查询表达式子句的元素置于单独的行。  
如果此规则设置为“false”，则需要将查询表达式子句的元素置于同一行。  

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

示例 .editorconfig 文件：  

```
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

#### <a name="indent">缩进选项</a>  
这些格式设置规则与是否使用缩进设置代码的格式有关。  

下表显示规则名称、适用的语言、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_indent_case_contents |  C# | true | Visual Studio 2017 v. 15.3  |
| csharp_indent_switch_labels |  C# | true | Visual Studio 2017 v. 15.3  |
| csharp_indent_labels |  C# | no_change | Visual Studio 2017 v. 15.3  |

**csharp\_indent\_case_contents**  
如果此规则设置为“true”，则缩进 `switch` 事例内容。  
如果此规则设置为“false”，则不缩进 `switch` 事例内容。  

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
如果此规则设置为“true”，则缩进 `switch` 标签。  
如果此规则设置为“false”，则不缩进 `switch` 标签。  

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

| 值 | 描述 |
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

示例 .editorconfig 文件：  

```
# CSharp formatting settings:
[*.cs]
csharp_indent_case_contents = true
csharp_indent_switch_labels = true
csharp_indent_labels = flush_left
``` 

#### <a name="spacing">间距选项</a>  
这些格式设置规则与是否使用空格字符设置代码的格式有关。  

下表显示规则名称、适用的语言、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_space_after_cast |  C# | false | Visual Studio 2017 v. 15.3  |
| csharp_space_after_keywords_in_control_flow_statements |  C# | true | Visual Studio 2017 v. 15.3  |
| csharp_space_between_method_declaration_parameter_list_parentheses |  C# | false | Visual Studio 2017 v. 15.3  |
| csharp_space_between_method_call_parameter_list_parentheses |  C# | false | Visual Studio 2017 v. 15.3  |
| csharp_space_between_parentheses |  C# | false | Visual Studio 2017 v. 15.3  |

**csharp\_space\_after_cast**  
如果此规则设置为“true”，则转换和值之间需要空格。  
如果此规则设置为“false”，则转换和值之间不需要空格。  

代码示例：

```csharp
// csharp_space_after_cast = true
int y = (int) x;

// csharp_space_after_cast = false
int y = (int)x;
```

**csharp_space_after_keywords_in_control_flow_statements**  
如果此规则设置为“true”，则在 `for` 循环等控制流语句中，关键字后需要空格。  
如果此规则设置为“false”，则在 `for` 循环等控制流语句中，关键字后不需要空格。  

代码示例：

```csharp
// csharp_space_after_keywords_in_control_flow_statements = true
for (int i;i<x;i++) { ... }

// csharp_space_after_keywords_in_control_flow_statements = false
for(int i;i<x;i++) { ... }
```

**csharp_space_between_method_declaration_parameter_list_parentheses**  
如果此规则设置为“true”，则在方法声明参数列表的左括号之后和右括号之前放置空格字符。  
如果此规则设置为“false”，则不要在方法声明参数列表的左括号之后和右括号之前放置空格字符。  

代码示例：

```csharp
// csharp_space_between_method_declaration_parameter_list_parentheses = true
void Bark( int x ) { ... }

// csharp_space_between_method_declaration_parameter_list_parentheses = false
void Bark(int x) { ... }
```

**csharp_space_between_method_call_parameter_list_parentheses**  
如果此规则设置为“true”，则在方法调用的左括号之后和右括号之前放置空格字符。  
如果此规则设置为“false”，则不要在方法调用的左括号之后和右括号之前放置空格字符。  

代码示例：

```csharp
// csharp_space_between_method_call_parameter_list_parentheses = true
MyMethod( argument );

// csharp_space_between_method_call_parameter_list_parentheses = false
MyMethod(argument);
```

**csharp_space_between_parentheses**  
此规则不接受“true”或“false”值；此规则接受下表中的值：  

| 值 | 描述 |
| ----- |:------------|
| control_flow_statements | 在控制流语句的括号之间放置空格 |
| 表达式 | 在表达式的括号之间放置空格 |
| type_casts | 在类型转换中的括号之间放置空格 |

代码示例：

```csharp
// csharp_space_between_parentheses = control_flow_statements
for( int i;i<x;i++ ) { ... }

// csharp_space_between_parentheses = expressions
var z = ( x * y ) - ( ( y - x ) * 3);

// csharp_space_between_parentheses = type_casts
int y = ( int )x;
```

示例 .editorconfig 文件：  

```
# CSharp formatting settings:
[*.cs]
csharp_space_after_cast = true
csharp_space_after_keywords_in_control_flow_statements = true
csharp_space_between_method_declaration_parameter_list_parentheses = true
csharp_space_between_method_call_parameter_list_parentheses = true
csharp_space_between_parentheses = control_flow_statements, type_casts
``` 

#### <a name="wrapping">换行选项</a>
这些格式设置规则与语句和代码块中单一行以及单独的行的使用有关。  

下表显示规则名称、适用的语言、默认值和第一个支持的 Visual Studio 版本：  

| 规则名称 | 适用的语言 | Visual Studio 默认值 | 支持的版本 |
| ----------- | -------------------- | ----------------------| ----------------  |
| csharp_preserve_single_line_statements |  C# | true | Visual Studio 2017 v. 15.3  |
| csharp_preserve_single_line_blocks |  C# | true | Visual Studio 2017 v. 15.3  |

**csharp_preserve_single_line_statements**   
如果此规则设置为“true”，则将语句和成员声明保留在同一行上。  
如果此规则设置为“false”，则将语句和成员声明保留在不同的行上。  

代码示例：  

```csharp
//csharp_preserve_single_line_statements = true
int i = 0; string name = "John";

//csharp_preserve_single_line_statements = false
int i = 0; 
string name = "John";
```

**csharp_preserve_single_line_blocks**  
如果此规则设置为“true”，则将代码块保留在单一的行上。  
如果此规则设置为“false”，则将代码块保留在单独的行上。  

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

示例 .editorconfig 文件：  

```
# CSharp formatting settings:
[*.cs]
csharp_preserve_single_line_statements = true
csharp_preserve_single_line_blocks = true
```

## <a name="naming-conventions"></a>命名约定  
命名约定与类、属性和方法等码位元素的命名有关。 例如，可以指定异步方法必须以“Async”结尾。 命名约定应从最具体到最抽象排序。 遇到的第一个可应用规则是唯一应用的规则。  

对于由“namingRuleTitle”标识的每个命名约定规则，必须指定该规则所应用的符号、命名样式和严重性：  
  
`dotnet_naming_rule.<namingRuleTitle>.symbols = <symbolTitle>`  
`dotnet_naming_rule.<namingRuleTitle>.style = <styleTitle>`  
`dotnet_naming_rule.<namingRuleTitle>.severity = none|suggestion|warning|error`  

### <a name="symbols"></a>符号
通过此属性标识一组要将命名规则应用到其中的符号：`dotnet_naming_rule.<namingRuleTitle>.symbols = <symbolTitle>`。 使用以下属性指定该组中所包含的符号类型、修饰符和可访问性级别：  

| 属性 | 可能的值 |
| ------------- |:-------------:|
| dotnet\_naming\_symbols.\<symbolTitle\>.applicable\_kinds | *、class、struct、interface、enum、property、method、field、event、namespace、delegate、type_parameter |
| dotnet\_naming\_symbols.\<symbolTitle\>.applicable_accessibilities | *、public、internal (C#)、friend (Visual Basic)、private、protected、protected\_internal (C#)、protected\_friend (Visual Basic) |
| dotnet\_naming\_symbols.\<symbolTitle\>.required\_modifiers | abstract (C#)、must_inherit (Visual Basic)、async、const、readonly、static (C#)、shared (Visual Basic) |  

### <a name="style"></a>样式
通过此属性标识要应用到一组符号中的命名样式：`dotnet_naming_rule.<namingRuleTitle>.style = <styleTitle>`。  

使用一个或多个以下属性指定命名样式：  

|  属性 | 可能的值 |
| ------------- |:-------------:|
| dotnet_naming_style.\<styleTitle\>.required_prefix | 必须出现在标识符开头的所需字符。 |  
| dotnet_naming_style.\<styleTitle\>.required_suffix | 必须出现在标识符结尾的所需字符。 |  
| dotnet_naming_style.\<styleTitle\>.word_separator | 标识符中字之间的所需字符。 | 
| dotnet_naming_style.\<styleTitle\>.capitalization | pascal_case、camel_case、first_word_upper、all_upper、all_lower |

> [!NOTE]
> 命名样式中必须指定大写样式，否则会忽略命名样式。  

#### <a name="severity"></a>严重性
使用此属性标识命名规则的严重性级别：`dotnet_naming_rule.<namingRuleTitle>.severity`。  

下表显示严重性值的选项：  

严重性 | 效果
------------ | -------------
无或无提示 | 如未遵循此样式，则不会向用户显示任何内容，但代码生成功能会以此样式生成代码。  
建议 | 如未遵循此样式，以建议形式向用户显示此样式（前两个字符下带点）。 编译时无任何效果。  
警告 | 如未遵循此样式，显示编译器警告。  
错误 | 如未遵循此样式，显示编译器错误。   

### <a name="example-editorconfig-file-with-naming-conventions"></a>具有命名约定的示例 .editorconfig 文件
```
# Dotnet Naming Conventions
[*.{cs,vb}] 
dotnet_naming_rule.async_methods_end_in_async.symbols  = any_async_methods
dotnet_naming_rule.async_methods_end_in_async.style    = end_in_async
dotnet_naming_rule.async_methods_end_in_async.severity = suggestion

dotnet_naming_symbols.any_async_methods.applicable_kinds           = method
dotnet_naming_symbols.any_async_methods.applicable_accessibilities = *
dotnet_naming_symbols.any_async_methods.required_modifiers         = async

dotnet_naming_style.end_in_async.required_suffix = Async
dotnet_naming_style.end_in_async.capitalization  = pascal_case
``` 

## <a name="see-also"></a>请参阅
[快速操作](../ide/quick-actions.md)  
[创建可移植的自定义编辑器选项](https://docs.microsoft.com/en-us/visualstudio/ide/create-portable-custom-editor-options)  
[.NET 编译器平台的 .editorconfig 文件](https://github.com/dotnet/roslyn/blob/master/.editorconfig)  
