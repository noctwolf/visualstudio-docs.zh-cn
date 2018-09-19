---
title: FxCop 代码分析和 FxCop 分析器
ms.date: 09/06/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: overview
helpviewer_keywords:
- code analysis FAQ
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: e05dd0e01254bf1222a8a7de497b11ec2a808bfb
ms.sourcegitcommit: b9a32c3d94b19e7344f4872bc026efd3157cf220
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46136363"
---
# <a name="frequently-asked-questions-about-fxcop-and-fxcop-analyzers"></a>有关 FxCop 和 FxCop 常见问题的分析器

可能会有点令人困惑，若要了解旧的 FxCop 和 FxCop 之间的差异的分析器。 本文旨在解决的问题可能有一些。

## <a name="whats-the-difference-between-legacy-fxcop-and-fxcop-analyzers"></a>旧的 FxCop 和 FxCop 之间的区别是什么分析器？

旧的 FxCop 在已编译的程序集上运行后期生成分析。 它作为名为一个单独的可执行文件运行**FxCopCmd.exe**。 FxCopCmd.exe 加载已编译的程序集，运行代码分析，然后报告结果 (或*诊断*)。

FxCop 分析器基于.NET 编译器平台 ("Roslyn")。 您[NuGet 包中安装它们](install-fxcop-analyzers.md#to-install-fxcop-analyzers-as-a-nuget-package)所引用的项目或解决方案。 FxCop 分析器运行源代码编译器执行过程基于分析。 在编译器进程中，或者托管 FxCop 分析器**csc.exe**或**vbc.exe**，并生成项目时运行的分析。 分析器结果以及编译器结果报告。

> [!NOTE]
> 此外可以[作为 Visual Studio 扩展安装 FxCop 分析器](install-fxcop-analyzers.md#to-install-fxcop-analyzers-as-a-vsix)。 在这种情况下，分析器执行，因为在代码编辑器中，键入，但它们不在生成时执行。 如果你想要作为持续集成 (CI) 的一部分运行 FxCop 分析器，它们以 NuGet 包的形式改为安装。

## <a name="does-the-run-code-analysis-command-run-fxcop-analyzers"></a>运行代码分析命令是否运行 FxCop 分析器？

不是。 当选择**分析** > **运行代码分析**在 Visual Studio 2017 中，它执行静态代码分析或旧的 FxCop。 **运行代码分析**基于 Roslyn 的分析器，包括基于 Roslyn 的 FxCop 分析器对没有影响。

## <a name="does-the-runcodeanalysis-msbuild-project-property-run-analyzers"></a>RunCodeAnalysis msbuild 项目属性是否运行分析器？

不是。 **RunCodeAnalysis**项目文件中的属性 (例如， *.csproj*) 只能用于执行旧的 FxCop。 运行调用后期生成 msbuild 任务**FxCopCmd.exe**。 这相当于选择**分析** > **运行代码分析**Visual Studio 中。

## <a name="so-how-do-i-run-fxcop-analyzers-then"></a>那么，如何然后运行 FxCop 分析器？

若要首先运行 FxCop 分析器[安装 NuGet 包](install-fxcop-analyzers.md)它们。 然后从 Visual Studio 或使用 msbuild 构建项目或解决方案。 警告和 FxCop 分析器生成的错误将出现在**错误列表**或命令窗口。

## <a name="see-also"></a>请参阅

- [.NET Compiler Platform 分析器的概述](roslyn-analyzers-overview.md)
- [开始使用分析器](fxcop-analyzers.yml)
- [安装 FxCop 分析器](install-fxcop-analyzers.md)
