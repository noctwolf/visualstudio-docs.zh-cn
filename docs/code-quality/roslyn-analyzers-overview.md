---
title: 在 Visual Studio 中的 Roslyn 分析器
ms.date: 03/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: overview
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 3d5836c0522ef97a634f44799934aab2750b3a45
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2018
ms.locfileid: "39511417"
---
# <a name="overview-of-net-compiler-platform-analyzers"></a>.NET Compiler Platform 分析器的概述

Visual Studio 2017 包括一组内置分析 C# 或 Visual Basic 代码，当您键入的.NET Compiler Platform 分析器。 你可以安装其他分析器以 Visual Studio 扩展，或在每个项目上作为 NuGet 包。 分析器查看代码样式、 代码质量和可维护性、 代码设计和其他问题。

如果分析器发现规则冲突，它们将报告作为在代码编辑器中同时*波浪*下有问题的代码，然后在**错误列表**。

许多分析程序规则，或*诊断*，具有一个或多个关联*代码修补程序*可以应用要更正此问题。 内置到 Visual Studio analyzer 诊断已应用相关联的代码修补程序。 代码修补程序所示的灯泡图标菜单中，以及其他类型的*快速操作*。 有关这些代码修补程序的信息，请参阅[常见快速操作](../ide/common-quick-actions.md)。

![分析器冲突和快速操作代码修补程序](../code-quality/media/built-in-analyzer-code-fix.png)

## <a name="roslyn-analyzers-vs-static-code-analysis"></a>与静态代码分析的 Roslyn 分析器

最终将取代.NET 编译器平台 ("Roslyn") 分析器[静态代码分析](../code-quality/code-analysis-for-managed-code-overview.md)托管代码。 许多静态代码分析规则都已被重新编写为 Roslyn 分析器诊断。

静态代码分析规则冲突，如出现在 Roslyn 分析器冲突**错误列表**。 此外，Roslyn 分析器冲突也会出现在代码编辑器中按*标记*下有问题的代码。 取决于颜色的波浪[严重性设置](../code-quality/use-roslyn-analyzers.md#rule-severity)的规则。 以下屏幕截图显示了三个冲突&mdash;一个红色、 一个绿色和一个灰色：

![在代码编辑器中的标记](media/diagnostics-severity-colors.png)

Roslyn 分析器在生成时，如静态代码分析，如果它已启用，但也可以随着您键入实时分析的代码 ！ Roslyn 分析器还可以提供不在编辑器中打开，如果启用的代码文件的设计时分析[完整解决方案分析](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md#to-toggle-full-solution-analysis)。

> [!NOTE]
> 生成时错误和警告从 Roslyn 分析器将仅显示是否分析器作为 NuGet 包安装。

不仅执行 Roslyn 分析器会报告相同类型的问题执行静态代码分析，而且它们便于您修复一个或所有文件或项目中的冲突的匹配项。 这些操作称为*代码修补程序*。 代码修补程序是特定于 IDE 的;在 Visual Studio 中，它们将作为[快速操作](../ide/quick-actions.md)。 并非所有分析器诊断都已应用相关联的代码修补程序。

> [!NOTE]
> 菜单选项**分析** > **运行代码分析**应用仅为静态代码分析。 此外，在项目的**代码分析**属性页**生成时启用代码分析**并**禁止显示生成代码的结果**复选框仅适用于静态代码分析。 它们对 Roslyn 分析器上的无效。

若要区分从 Roslyn 分析器的冲突和中的静态代码分析**错误列表**，看看**工具**列。 工具值是否与其中一个中的分析器程序集匹配**解决方案资源管理器**，例如**Microsoft.CodeQuality.Analyzers**，冲突来自 Roslyn 分析器。 否则，冲突源自静态代码分析。

![错误列表中的工具列](media/code-analysis-tool-in-error-list.png)

## <a name="nuget-package-versus-vsix-extension"></a>与 VSIX 扩展的 NuGet 包

.NET compiler Platform 分析器可以是作为 Visual Studio 扩展安装的每个项目通过 NuGet 包或 Visual Studio 范围。 有的这两种方法之间的一些关键行为差异[安装分析器](../code-quality/install-roslyn-analyzers.md)。

### <a name="scope"></a>范围

如果作为 Visual Studio 扩展安装分析器，这些应用在解决方案级别中，于 Visual Studio 的所有实例。 如果你安装分析器作为 NuGet 包，这是首选的方法，它们仅应用于项目的 NuGet 包的安装位置。 在团队环境中，分析器作为 NuGet 包安装是中的范围内*所有开发人员*，在处理该项目。

### <a name="build-errors"></a>生成错误

能够在生成时，包括通过命令行或作为一部分的持续集成 (CI) 生成，强制执行规则作为 NuGet 包安装分析器。 分析器警告和错误不会显示在生成报告如果作为扩展安装分析器。

下面的屏幕截图显示了构建包含分析器规则冲突的项目的命令行生成输出：

![与规则冲突的 MSBuild 输出](media/command-line-build-analyzers.png)

### <a name="rule-severity"></a>规则严重性

不能从已作为 Visual Studio 扩展安装的分析器设置的规则的严重性。 若要配置[规则严重性](../code-quality/use-roslyn-analyzers.md#rule-severity)，作为 NuGet 包安装分析器。

## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [在 Visual Studio 中安装 Roslyn 分析器](../code-quality/install-roslyn-analyzers.md)

> [!div class="nextstepaction"]
> [在 Visual Studio 中使用 Roslyn 分析器](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>请参阅

- [在 Visual Studio 中的快速操作](../ide/quick-actions.md)
- [编写 Roslyn 分析器](../extensibility/getting-started-with-roslyn-analyzers.md)
- [.NET 编译器平台 SDK](/dotnet/csharp/roslyn-sdk/)