---
title: Visual Studio 中的 Roslyn 分析器
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
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2018
ms.locfileid: "39511417"
---
# <a name="overview-of-net-compiler-platform-analyzers"></a>.NET Compiler Platform 分析器概述

Visual Studio 2017 包括一系列内置的 .NET Compiler Platform 分析器，这些分析器在用户键入时分析 C# 或 Visual Basic 代码。 可以将其他分析器作为 Visual Studio 扩展安装，或在每个项目上作为 NuGet 包安装。 分析器关注代码样式、代码质量和可维护性、代码设计和其他问题。

如果分析器发现规则冲突，将同时在代码编辑器（违规代码下方有波浪线）和错误列表中报告。

许多分析器规则或诊断都有一个或多个相关的代码修复程序，可以应用它们来纠正问题。 Visual Studio 中内置的每个分析器诊断都有关联的代码修复。 代码修复以及其他类型的快速操作显示在灯泡图标菜单中。 有关这些代码修复的信息，请参阅[常见快速操作](../ide/common-quick-actions.md)。

![分析器冲突和快速操作代码修复](../code-quality/media/built-in-analyzer-code-fix.png)

## <a name="roslyn-analyzers-vs-static-code-analysis"></a>Roslyn 分析器与静态代码分析

.NET Compiler Platform ("Roslyn") 分析器最终将取代托管代码的[静态代码分析](../code-quality/code-analysis-for-managed-code-overview.md)。 许多静态代码分析规则都已被重新编写为 Roslyn 分析器诊断。

与静态代码分析规则冲突一样，Roslyn 分析器冲突显示在错误列表中。 此外，Roslyn 分析器冲突也会在代码编辑器中以波浪线的形式显示在违规代码下。 规则的[严重性设置](../code-quality/use-roslyn-analyzers.md#rule-severity)决定波浪线的颜色。 以下屏幕截图显示了三个冲突 &mdash; 一个为红色、一个绿色为以及一个为灰色：

![代码编辑器中的波浪线](media/diagnostics-severity-colors.png)

Roslyn 分析器在生成时分析代码，比如静态代码分析（如果启用），但还可随你键入保持运行！ 如果启用[完整解决方案分析](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md#to-toggle-full-solution-analysis)，Roslyn 分析器还可以提供编辑器中未打开的代码文件的设计时分析。

> [!NOTE]
> 仅当分析仪作为 NuGet 软件包安装时，才会显示 Roslyn 分析器的生成时错误和警告。

Roslyn 分析器不仅会报告静态代码分析也会报告的相同类型的问题，而且还可以轻松修复文件或项目中冲突的一次发生或全部发生。 这些操作称为代码修复。 代码修复是特定于 IDE 的；在 Visual Studio 中，它们以[快速操作](../ide/quick-actions.md)的方式实现。 并非所有分析器诊断都有相关联的代码修复。

> [!NOTE]
> 菜单选项“分析” > “运行代码分析”仅适用于静态代码分析。 此外，在项目的“代码分析”属性页上，“生成时启用代码分析”和“禁止显示所生成代码的结果”复选框仅适用于静态代码分析。 它们在 Roslyn 分析器上无效。

要区分“错误列表”中来自 Roslyn 分析器的冲突和来自静态代码分析的冲突，请查看“工具”列。 如果“工具”值与“解决方案资源管理器”中的某个分析器程序集匹配，例如 Microsoft.CodeQuality.Analyzers，则冲突来自 Roslyn 分析器。 否则，冲突源自静态代码分析。

![错误列表中的工具列](media/code-analysis-tool-in-error-list.png)

## <a name="nuget-package-versus-vsix-extension"></a>NuGet 包与 VSIX 扩展

.NET Compiler Platform 分析器可以通过 NuGet 包按项目安装，也可以作为 Visual Studio 扩展安装在 Visual Studio 内。 这两种[安装分析器](../code-quality/install-roslyn-analyzers.md)方法之间存在一些关键行为差异。

### <a name="scope"></a>范围

如果将分析器安装为 Visual Studio 扩展，则它们将在解决方案级别应用于 Visual Studio 的所有实例。 如果将分析器安装为 NuGet 包（这是首选方法），它们仅适用于安装了 NuGet 软件包的项目。 在团队环境中，作为 NuGet 包安装的分析器适用于处理该项目的所有开发人员。

### <a name="build-errors"></a>生成错误

要在生成时强制执行规则，包括通过命令行执行或作为持续集成 (CI) 生成的一部分来执行，请将分析器安装为 NuGet 包。 如果将分析器作为扩展安装，则分析器警告和错误不会显示在生成报告中。

以下屏幕截图显示了生成包含分析器规则冲突的项目时的命令行生成输出：

![带规则冲突的 MSBuild 输出](media/command-line-build-analyzers.png)

### <a name="rule-severity"></a>规则严重性

无法设置作为 Visual Studio 扩展安装的分析器的规则严重性。 若要配置[规则严重性](../code-quality/use-roslyn-analyzers.md#rule-severity)，则应将分析器安装为 NuGet 包。

## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [在 Visual Studio 中安装 Roslyn 分析器](../code-quality/install-roslyn-analyzers.md)

> [!div class="nextstepaction"]
> [在 Visual Studio 中使用 Roslyn 分析器](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>请参阅

- [Visual Studio 中的快速操作](../ide/quick-actions.md)
- [编写 Roslyn 分析器](../extensibility/getting-started-with-roslyn-analyzers.md)
- [.NET Compiler Platform SDK](/dotnet/csharp/roslyn-sdk/)