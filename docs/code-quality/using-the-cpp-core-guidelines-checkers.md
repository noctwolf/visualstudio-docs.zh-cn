---
title: 使用 C++ 核心准则检查程序
ms.date: 08/14/2018
ms.topic: conceptual
author: mikeblome
ms.author: mblome
manager: wpickett
dev_langs:
- CPP
ms.openlocfilehash: 15877cbaed093eab2cf436ed5122c80b9e135800
ms.sourcegitcommit: 87d7123c09812534b7b08743de4d11d6433eaa13
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57223346"
---
# <a name="using-the-c-core-guidelines-checkers"></a>使用 C++ 核心准则检查程序

C + + Core Guidelines 了一可移植的指导原则、 规则和有关在 c + + 创建的 c + + 专家和设计器中编写代码的最佳做法。 Visual Studio 当前支持 c + + 作为其代码分析工具的一部分的这些规则的子集。 核心准则检查器在 Visual Studio 2017 和 Visual Studio 2019，默认情况下已安装并且位于[可用作 Visual Studio 2015 的 NuGet 包](#vs2015_corecheck)。

## <a name="the-c-core-guidelines-project"></a>C + + 核心准则项目

C + + Core Guidelines 由 Bjarne Stroustrup 和其他人创建的它是如何安全有效地使用现代 c + + 的指南。 指南强调了静态类型安全性和资源安全。 他们确定消除或最小化的语言，最容易出错的各个部分的方法，并建议如何使代码更简单和更高的性能可靠的方式。 由标准 c + + 基础维护这些指导原则。 若要了解详细信息，请参阅本文档中， [c + + Core Guidelines](http://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)，并在访问 c + + Core Guidelines 文档项目文件[GitHub](https://github.com/isocpp/CppCoreGuidelines)。

## <a name="enable-the-c-core-check-guidelines-in-code-analysis"></a>启用代码分析中的 c + + Core Check 准则
 可以通过选择您的项目中启用代码分析**生成时启用代码分析**中的复选框**代码分析**一部分**属性页**对话框你的项目。

 ![代码分析常规设置的属性页](media/cppcorecheck_codeanalysis_general.png)

 C + + Core Check 规则的子集是默认包含在中运行的 Microsoft 本机建议规则集时启用代码分析。 若要启用其他 Core Check 规则，单击下拉列表中，然后选择你想要包括哪些规则集：

 ![下拉列表中的其他 c + + Core Check 规则集](media/cppcorecheck_codeanalysis_extensions.png)

## <a name="examples"></a>示例
 下面是 c + + Core Check 规则可以找到问题的一些示例：

```cpp
// CoreCheckExample.cpp
// Add CppCoreCheck package and enable code analysis in build for warnings.

int main()
{
    int arr[10];           // warning C26494
    int* p = arr;          // warning C26485

    [[gsl::suppress(bounds.1)]] // This attribute suppresses Bounds rule #1
    {
        int* q = p + 1;    // warning C26481 (suppressed)
        p = q++;           // warning C26481 (suppressed)
    }

    return 0;
}
```

此示例演示了几个 c + + Core Check 规则可以找到的警告：

- C26494 是规则 Type.5:始终初始化对象。

- C26485 是规则 Bounds.3:没有数组指针的衰减。

- C26481 是规则 Bounds.1:请勿使用指针算法。 请改用 `span`。

如果安装并启用时编译此代码前, 两个警告是输出，但禁止第三个 c + + Core Check 代码分析规则集。 下面是示例代码的生成输出：

```Output
1>------ Build started: Project: CoreCheckExample, Configuration: Debug Win32 ------
1>  CoreCheckExample.cpp
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.exe
1>  CoreCheckExample.vcxproj -> C:\Users\username\documents\visual studio 2015\Projects\CoreCheckExample\Debug\CoreCheckExample.pdb (Full PDB)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(6): warning C26494: Variable 'arr' is uninitialized. Always initialize an object. (type.5: http://go.microsoft.com/fwlink/p/?LinkID=620421)
c:\users\username\documents\visual studio 2015\projects\corecheckexample\corecheckexample\corecheckexample.cpp(7): warning C26485: Expression 'arr': No array to pointer decay. (bounds.3: http://go.microsoft.com/fwlink/p/?LinkID=620415)
========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
```

C + + Core Guidelines 是为了帮助您编写更好、 更安全代码。 但是，如果有一个规则或配置文件不应应用的实例时，很容易在代码中直接取消。 可以使用`gsl::suppress`属性以防止 c + + Core Check 检测和报告任何违反了下面的代码块中的规则。 可以将标记单个语句，若要禁止显示特定的规则。 甚至可以禁止整个绑定配置文件，方法是编写`[[gsl::suppress(bounds)]]`而不包括特定的规则数。

## <a name="supported-rule-sets"></a>支持的规则集
新规则添加到 c + + 核心准则检查程序，可能会增加为预先存在的代码生成的警告数。 预定义的规则集可用于筛选哪些类型的规则来启用。
参考主题的最多的规则正在[Visual Studio c + + Core 检查引用](code-analysis-for-cpp-corecheck.md)。

截至 Visual Studio 2017 版本 15.3 中，支持的规则集是：
- **所有者指针规则**强制实施[资源管理检查与所有者相关<T>c + + Core Guidelines 中](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)。

- **常量规则**强制实施[c + + Core Guidelines 中常量相关的检查](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability)。

- **原始指针规则**强制实施[资源管理检查 c + + Core Guidelines 中的与原始指针](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)。

- **唯一指针规则**强制实施[资源管理检查 c + + Core Guidelines 中具有唯一指针语义的类型相关的](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)。

- **绑定规则**强制实施[限制配置文件的 c + + Core Guidelines](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile)。

- **键入规则**强制实施[键入配置文件的 c + + Core Guidelines](http://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile)。

**Visual Studio 2017 版本 15.5**：

- **类规则**专注于正确使用的特殊成员函数和虚拟规范的几个规则。 这是检查建议的子集[类和类层次结构](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-class)。
- **并发规则**捕获错误声明临界对象的单个规则。 有关详细信息，请参阅[与并发相关的指导原则](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-concurrency)。
- **声明规则**几个中的规则[接口准则](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-interfaces)声明全局变量，重点。
- **函数的规则**采用的帮助的两个检查`noexcept`说明符。 这是一部分的准则[清除函数设计和实现](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-functions)。
- **共享指针规则**的一部分[资源管理](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-resource)准则强制技术，我们添加了特定于如何共享指针的几个规则都传递到函数中或在本地使用。
- **样式规则**一个简单但很重要检查，bans 利用[goto](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-goto)。 这是改进的编码样式和使用表达式和语句在 c + + 中的第一步。

**Visual Studio 2017 15.6 版**：

- **算术规则**规则，以检测算术[溢出](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-overflow)，[有符号的无符号操作](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-unsigned)并[位操作](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Res-nonnegative)。

您可以选择限制为只是一个或多个组的警告。 **本机最小**并**本机建议**集包括除了其他 PREfast 检查 c + + Core Check 规则的规则。 若要查看可用的规则集，请打开项目属性对话框中，选择**代码 Analysis\General**，打开中的下拉列表**规则集**组合框，以及选择**选择多个规则集**. 有关在 Visual Studio 中使用规则集的详细信息，请参阅[使用规则集组合代码分析规则](using-rule-sets-to-group-code-analysis-rules.md)。

## <a name="macros"></a>宏

C + + 核心准则检查程序附带的标头文件，定义更加轻松地禁止显示整个类别的代码中的警告的宏：

```cpp
ALL_CPPCORECHECK_WARNINGS
CPPCORECHECK_TYPE_WARNINGS
CPPCORECHECK_RAW_POINTER_WARNINGS
CPPCORECHECK_CONST_WARNINGS
CPPCORECHECK_OWNER_POINTER_WARNINGS
CPPCORECHECK_UNIQUE_POINTER_WARNINGS
CPPCORECHECK_BOUNDS_WARNINGS
```

这些宏与规则集相对应，并且扩展为以空格分隔的警告编号的列表。 通过使用相应的杂注构造，可以配置是有趣的项目的有效规则集或一段代码。 在以下示例中，代码分析警告仅关于缺少常量修饰符：

```cpp
#include <CppCoreCheck\Warnings.h>
#pragma warning(disable: ALL_CPPCORECHECK_WARNINGS)
#pragma warning(default: CPPCORECHECK_CONST_WARNINGS)
```

## <a name="attributes"></a>特性

Microsoft Visual c + + 编译器提供有限的支持，为 GSL 禁止显示属性。 可用来禁止显示警告表达式和函数内的块语句上。

```cpp
// Suppress only warnings from the 'r.11' rule in expression.
[[gsl::suppress(r.11)]] new int;

// Suppress all warnings from the 'r' rule group (resource management) in block.
[[gsl::suppress(r)]]
{
    new int;
}

// Suppress only one specific warning number.
// For declarations, you may need to use the surrounding block.
// Macros are not expanded inside of attributes.
// Use plain numbers instead of macros from the warnings.h.
[[gsl::suppress(26400)]]
{
    int *p = new int;
}
```

## <a name="suppressing-analysis-by-using-command-line-options"></a>使用命令行选项取消分析

而不是 #pragmas，您可以使用命令行选项在该文件的属性页中禁止显示警告的一个项目或单个文件。 例如，若要禁用警告 26400 文件：

1. 右键单击该文件中的**解决方案资源管理器**

2. 选择**属性 |C / C + + |命令行**

3. 在中**其他选项**窗口中，添加`/wd26400`。

可以使用命令行选项以暂时禁用通过指定文件的所有代码分析`/analyze-`。 这会生成警告*D9025 重写 /analyze 与 / 分析-*，这将提醒你重新启用代码分析更高版本。

## <a name="corecheck_per_file"></a> 启用特定项目文件上的 c + + 核心准则检查器

有时可能会对进行专注于代码分析和使用 Visual Studio IDE 仍然有用。 下面的示例方案可用于大型项目，以保存生成时，使其能够更轻松地筛选结果：

1. 在命令行界面中设置`esp.extension`和`esp.annotationbuildlevel`环境变量。
2. 若要继承这些变量，请从命令行界面启动 Visual Studio。
3. 加载你的项目并打开其属性。
4. 启用代码分析，选取合适的规则集，但不是启用代码分析扩展。
5. 转到你想要使用 c + + 核心准则检查程序进行分析并打开其属性的文件。
6. 选择**C / C + + \Command 行选项**并添加 `/analyze:plugin EspXEngine.dll`
7. 禁用使用预编译标头 (**C / C + + 标头 \Precompiled**)。 这是必需的因为扩展引擎可能会尝试从预编译标头 (PCH); 读取其内部信息如果使用默认项目选项编译 PCH，它将不兼容。
8. 重新生成项目。 常见 PREFast 检查应运行的所有文件。 默认情况下不启用 c + + 核心准则检查程序，因为它只应在配置为使用该文件上运行。

## <a name="how-to-use-the-c-core-guidelines-checker-outside-of-visual-studio"></a>如何使用 Visual Studio 外部的 c + + 核心准则检查器

可以在自动生成中使用 c + + Core Guidelines 检查。

### <a name="msbuild"></a>MSBuild
 本机代码分析检查器 (PREfast) 已集成到 MSBuild 环境由自定义目标文件。 可以使用项目属性来启用它，并添加 c + + 核心准则检查器 （这基于 PREfast）：

 ```xml
  <PropertyGroup>
    <EnableCppCoreCheck>true</EnableCppCoreCheck>
    <CodeAnalysisRuleSet>CppCoreCheckRules.ruleset</CodeAnalysisRuleSet>¬¬
    <RunCodeAnalysis>true</RunCodeAnalysis>
  </PropertyGroup>
```

请确保添加这些属性，然后才能 Microsoft.Cpp.targets 文件导入。 可以选择特定的规则集或创建自定义规则集或使用默认规则集包含其他 PREfast 检查。

可以通过使用相同的方法仅在指定的文件上运行 c + + Core Checker[前面所述](#corecheck_per_file)，但使用 MSBuild 文件。 可以使用设置环境变量`BuildMacro`项：

```xml
<ItemGroup>
    <BuildMacro Include="Esp_AnnotationBuildLevel">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>Ignore</Value>
    </BuildMacro>
    <BuildMacro Include="Esp_Extensions">
      <EnvironmentVariable>true</EnvironmentVariable>
      <Value>CppCoreCheck.dll</Value>
    </BuildMacro>
</ItemGroup>
```

如果不想要修改项目文件，则可以在命令行上传递属性：

```cmd
msbuild /p:EnableCppCoreCheck=true /p:RunCodeAnalysis=true /p:CodeAnalysisRuleSet=CppCoreCheckRules.ruleset ...
```

### <a name="non-msbuild-projects"></a>非 MSBuild 项目

如果使用不依赖于 MSBuild 的生成系统仍可运行检查器中，但您需要先获取熟悉的代码分析引擎配置某些内部结构。 这些内部结构不能保证将来支持。

您必须设置几个环境变量和编译器使用适当的命令行选项。 它是更好的做法，以便无需搜索特定的编译器的路径，包括目录等的"本机工具命令提示"环境下工作。

1. **环境变量**
   - `set esp.extensions=cppcorecheck.dll` 这可以使引擎加载的 c + + Core Guidelines 模块。
   - `set esp.annotationbuildlevel=ignore` 这将禁用处理 SAL 注释的逻辑。 批注不会影响在 c + + 核心准则检查器中，代码分析，但它们的处理时间 （有时会很长时间）。 此设置是可选的但强烈建议采用。
   - `set caexcludepath=%include%` 我们强烈建议你禁用警告将在标准标头上触发。 可以添加更多路径，例如在项目中的通用标头的路径。
2. **命令行选项**
   - `/analyze`  启用代码分析 (也可以考虑使用 /analyze： 仅和 /analyze: quiet)。
   - `/analyze:plugin EspXEngine.dll` 此选项将代码分析扩展引擎加载到 PREfast。 此引擎加载 c + + 核心准则检查程序。

## <a name="use-the-guideline-support-library"></a>使用准则支持库
 准则支持库旨在帮助你遵循核心指导原则。 GSL 包括使您易出错的构造替换为更安全的替代方法的定义。 例如，您可以替换`T*, length`对参数使用`span<T>`类型。 GSL 位于[ http://www.nuget.org/packages/Microsoft.Gsl ](http://www.nuget.org/packages/Microsoft.Gsl)。 库是开源的因此可以查看的源、 进行注释，或者提供。 可以在找到的项目[ https://github.com/Microsoft/GSL ](https://github.com/Microsoft/GSL)。

## <a name="vs2015_corecheck"></a> 在 Visual Studio 2015 项目中使用 c + + Core Check 准则

如果使用 Visual Studio 2015，默认情况下未安装 c + + Core Check 代码分析规则集。 可以让 Visual Studio 2015 中的 c + + Core Check 代码分析工具之前，必须执行一些附加步骤。 Microsoft 提供支持的 Visual Studio 2015 项目使用的 Nuget 包。 应用程序包名为 Microsoft.CppCoreCheck，并可通过[ http://www.nuget.org/packages/Microsoft.CppCoreCheck ](http://www.nuget.org/packages/Microsoft.CppCoreCheck)。 此软件包要求必须至少安装 Visual Studio 2015 Update 1。

包还将作为依赖项，仅限标头的准则支持库 (GSL) 安装另一个包。 GSL，还可以在 GitHub 上[ https://github.com/Microsoft/GSL ](https://github.com/Microsoft/GSL)。

由于加载代码分析规则的方式，必须 Microsoft.CppCoreCheck NuGet 包安装到你想要在 Visual Studio 2015 中检查每个 c + + 项目。

### <a name="to-add-the-microsoftcppcorecheck-package-to-your-project-in-visual-studio-2015"></a>若要将 Microsoft.CppCoreCheck 包添加到 Visual Studio 2015 中的项目

1. 在中**解决方案资源管理器**，右键单击你想要将包添加到解决方案中打开你的项目的上下文菜单。 选择**管理 NuGet 包**以打开**NuGet 包管理器**。

2. 在中**NuGet 包管理器**窗口中，搜索 Microsoft.CppCoreCheck。

    ![Nuget 包管理器窗口中显示了 CppCoreCheck 包](../code-quality/media/cppcorecheck_nuget_window.png)

3. 选择 Microsoft.CppCoreCheck 包，然后选择**安装**按钮将规则添加到你的项目。

   NuGet 包添加了其他 MSBuild *.targets*到你在你的项目中启用代码分析时调用的项目文件。 这 *.targets*文件将作为附加扩展 c + + Core Check 规则添加到 Visual Studio 代码分析工具。 安装包时，可以使用属性页对话框启用或禁用发布和试验性规则。

## <a name="see-also"></a>请参阅

- [Visual Studio c + + Core Check 参考](code-analysis-for-cpp-corecheck.md)