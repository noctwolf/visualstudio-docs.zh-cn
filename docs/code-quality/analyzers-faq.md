---
title: 与分析器的 EditorConfig
ms.date: 03/11/2019
ms.topic: conceptual
helpviewer_keywords:
- analyzers, faq
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bec9296f15c48cf3b327c78cd0ce7d57adafa002
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57874657"
---
# <a name="analyzers-faq"></a>分析器常见问题

此页包含有关 Roslyn 分析器在 Visual Studio 中一些常见问题的解答。

## <a name="roslyn-analyzers-versus-editorconfig"></a>与.editorconfig Roslyn 分析器

**问：**:应使用 Roslyn 分析器或.editorconfig 代码样式？

**答**：Roslyn 分析器和.editorconfig 文件工作手中手。 在定义代码样式[.editorconfig 文件中](../ide/editorconfig-code-style-settings-reference.md)或在[文本编辑器选项](../ide/code-styles-and-quick-actions.md)页上，要实际配置内置到 Visual Studio 中的 Roslyn 分析器。 EditorConfig 文件还可用于配置一些第三方分析器的程序包，例如[FxCop 分析器](configure-fxcop-analyzers.md)。

## <a name="editorconfig-versus-rule-sets"></a>与规则集的 EditorConfig

**问：**:应配置使用规则集或.editorconfig 文件我分析器？

**答**：规则集和.editorconfig 文件是互相排斥的方法可用于配置分析器。 它们可以共存。 [规则集](analyzer-rule-sets.md)让您可以启用和禁用规则并设置其严重程度。 EditorConfig 文件未提供其他方法来配置规则。 适用于 FxCop 分析器.editorconfig 文件让你[定义哪些类型的代码分析](fxcop-analyzer-options.md)。 对于内置到 Visual Studio 分析器，.editorconfig 文件让你[定义首选的代码样式](../ide/editorconfig-code-style-settings-reference.md)代码库。

除了规则集和.editorconfig 文件，某些第三方分析器配置通过使用标记为文本文件[其他文件](../ide/build-actions.md#build-action-values)为C#和 VB 编译器。

> [!NOTE]
> 不能使用 EditorConfig 文件配置静态代码分析规则，而规则集。

## <a name="analyzers-in-ci-builds"></a>在 CI 生成中的分析器

**问：**:分析器是否在持续集成 (CI) 生成工作？

**答**：可以。 适用于从 NuGet 包安装的分析器，这些规则是[在生成时强制实施](roslyn-analyzers-overview.md#build-errors)，其中包括在 CI 生成过程。 从这两个 CI 生成方面规则配置中使用的分析器[规则集](analyzer-rule-sets.md)并[.editorconfig 文件](configure-fxcop-analyzers.md)。 目前，内置到 Visual Studio 中的代码分析器不是作为 NuGet 包，可用，因此这些规则也不会强制在 CI 生成。

## <a name="ide-analyzers-versus-stylecop"></a>StyleCop 与 IDE 分析器

**问：**:在 Visual Studio IDE 代码分析器和 StyleCop 分析器之间的区别是什么？

**答**：Visual Studio IDE 包括内置分析器，查找这两种代码样式和质量问题。 这些规则帮助您使用新语言功能，因为它们暴露出来并提高你的代码的可维护性。 不断更新，IDE 分析器随每个 Visual Studio 版本。

[StyleCop 分析器](https://github.com/DotNetAnalyzers/StyleCopAnalyzers)是第三方分析器作为 NuGet 包安装，在代码中的样式一致性检查。 一般情况下，StyleCop 规则可以设置个人首选项代码基而无需做出推荐一种样式。

## <a name="analyzers-versus-static-code-analysis"></a>分析器与静态代码分析

**问：**:分析器和静态代码分析之间的区别是什么？

**答**：分析器分析源代码实时和期间编译，而静态代码分析将分析二进制文件后完成生成。 有关详细信息，请参阅[与静态代码分析的 Roslyn 分析器](roslyn-analyzers-overview.md#roslyn-analyzers-vs-static-code-analysis)并[FxCop 分析器常见问题解答](fxcop-analyzers-faq.md)。

## <a name="see-also"></a>请参阅

- [分析器概述](roslyn-analyzers-overview.md)
- [EditorConfig 的 .NET 编码约定设置](../ide/editorconfig-code-style-settings-reference.md)