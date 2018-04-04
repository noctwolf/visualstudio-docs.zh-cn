---
title: Visual Studio 中的 Roslyn 分析器 |Microsoft 文档
ms.date: 03/26/2018
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis, managed code
- analyzers
- Roslyn analyzers
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 35b052c795ae10b7d7c4f96c8c4fce72ecbee839
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="overview-of-net-compiler-platform-analyzers"></a>.NET Compiler Platform 分析器的概述

Visual Studio 2017 包括分析你的 C# 或 Visual Basic 代码，当您键入的.NET Compiler Platform 分析器一内置组。 你可以安装其他分析器为 Visual Studio 扩展，或根据每个项目作为 NuGet 程序包。 分析器查看代码样式、 代码质量和可维护性、 代码设计和其他问题。

如果分析器发现规则冲突，它们会报告同时在代码编辑器中按*波浪*下有问题的代码中，然后在**错误列表**。

许多分析程序规则，或*诊断*，具有一个或多个关联*代码修复*可以应用以更正此问题。 内置于 Visual Studio 的分析器诊断具有关联的代码修复。 显示在灯泡图标菜单中，以及其他类型的代码修复*快速操作*。 有关这些代码修补程序的信息，请参阅[常见快速操作](../ide/common-quick-actions.md)。

![分析器冲突和快速操作代码修复](../code-quality/media/built-in-analyzer-code-fix.png)

## <a name="roslyn-analyzers-vs-static-code-analysis"></a>Roslyn 分析器与静态代码分析

.NET compiler Platform ("Roslyn") 分析器最终将取代[静态代码分析](../code-quality/code-analysis-for-managed-code-overview.md)用于托管代码。 许多静态代码分析规则具有已被重写为 Roslyn 分析器诊断。

静态代码分析规则冲突，如 Roslyn 分析器冲突出现在**错误列表**。 此外，Roslyn 分析器冲突也会出现在代码编辑器中按*标记*有问题代码下面。 颜色的波浪取决于[严重性设置](../code-quality/use-roslyn-analyzers.md#rule-severity)的规则。 以下屏幕截图显示三个冲突&mdash;一个红色、 一个绿色和一个灰色：

![在代码编辑器中的标记](media/diagnostics-severity-colors.png)

Roslyn 分析器在生成期间，如静态代码分析，如果它已启用，但是还实时键入时分析的代码 ！ Roslyn 分析器还可以提供设计时分析的代码文件，如果启用不在编辑器中打开[完整解决方案分析](../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md#to-toggle-full-solution-analysis)。

> [!NOTE]
> 生成时错误和警告从 Roslyn 分析器将仅显示是否分析器将安装为 NuGet 包。

不仅执行 Roslyn 分析器报告相同类型的问题执行静态代码分析，而且它们便于你修复一个，或所有匹配项的文件或项目中的冲突。 这些操作被称为*代码修复*。 代码修补程序是特定于 IDE 的;在 Visual Studio 中，它们以实现[快速操作](../ide/quick-actions.md)。 并非所有分析器诊断都具有关联的代码修复。

> [!NOTE]
> 菜单选项**分析** > **运行代码分析**适用仅为静态代码分析。 此外，在项目的**代码分析**属性页中，**生成时启用代码分析**和**禁止显示生成代码产生的结果**复选框仅适用于静态代码分析。 它们具有 Roslyn 分析器不会影响。

若要区分从 Roslyn 分析器冲突和中的静态代码分析**错误列表**，查看**工具**列。 工具值是否与中的分析器程序集之一匹配**解决方案资源管理器**，例如**Microsoft.CodeQuality.Analyzers**，冲突来自 Roslyn 分析器。 否则，冲突源自静态代码分析。

![错误列表中的工具列](media/code-analysis-tool-in-error-list.png)

## <a name="nuget-package-vs-extension"></a>与扩展的 NuGet 包

.NET compiler Platform 分析器可以为 Visual Studio 扩展安装每个项目通过 NuGet 包或 Visual Studio 级。 有之间的这两种方法的一些关键行为差异[安装分析器](../code-quality/install-roslyn-analyzers.md)。

### <a name="scope"></a>范围

如果为 Visual Studio 扩展安装分析器，这些应用解决方案级别中，于 Visual Studio 的所有实例。 如果你安装分析器作为 NuGet 程序包，这是首选的方法，它们仅适用于项目安装 NuGet 包的位置。 在团队环境分析器作为 NuGet 包安装都位于作用域为*所有开发人员*，在项目的工作。

### <a name="build-errors"></a>生成错误

要让在生成时，包括通过命令行或作为一部分持续集成 (CI) 生成，强制执行的规则可作为 NuGet 程序包安装分析器。 分析器警告和错误不显示在生成报告如果作为扩展安装分析器。

下面的屏幕截图显示生成包含分析器规则冲突的项目的命令行生成的输出：

![MSBuild 输出与规则冲突](media/command-line-build-analyzers.png)

### <a name="rule-severity"></a>规则严重性

从 Visual Studio 扩展中已安装的分析器，不能设置规则的严重性。 若要配置[规则严重性](../code-quality/use-roslyn-analyzers.md#rule-severity)，作为 NuGet 程序包安装分析器。

## <a name="next-steps"></a>后续步骤

- [在 Visual Studio 中安装 Roslyn 分析器](../code-quality/install-roslyn-analyzers.md)
- [使用 Visual Studio 中的 Roslyn 分析器](../code-quality/use-roslyn-analyzers.md)

## <a name="see-also"></a>请参阅

- [Visual Studio 中的快速操作](../ide/quick-actions.md)
- [编写你自己 Roslyn 分析器](../extensibility/getting-started-with-roslyn-analyzers.md)
- [.NET compiler Platform SDK](/dotnet/csharp/roslyn-sdk/)