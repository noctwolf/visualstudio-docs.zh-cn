---
title: 在 Visual Studio 中的托管代码的代码分析
ms.date: 03/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.projectpropertypages.codeanalysis
helpviewer_keywords:
- code analysis, managed code
- managed code, code analysis
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: ad1b093c224e37ce53dc77472518d03f2dc8093b
ms.sourcegitcommit: 28909340cd0a0d7cb5e1fd29cbd37e726d832631
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44320808"
---
# <a name="overview-of-code-analysis-for-managed-code"></a>托管代码的代码分析概述

Visual Studio 2017 以两种方式分析托管代码：一种是使用传统的托管程序集 *FxCop* 静态分析，另一种是使用 .NET Compiler Platform **分析器。本主题介绍 FxCop 静态代码分析。若要详细了解如何使用 .NET Compiler Platform 分析器来分析代码，请参阅 [Roslyn 分析器概述](../code-quality/roslyn-analyzers-overview.md)。

针对托管代码的代码分析用于分析托管程序集并报告有关程序集的信息，例如违反 Microsoft .NET Framework 设计指南中规定的编程和设计准则。

分析工具将它在分析期间执行的检查表示为警告消息。 警告消息标识任何相关的编程和设计问题，如有可能，还提供有关如何修复问题的信息。

> [!NOTE]
> Visual Studio 中的 .NET Core 和 .NET Standard 项目不支持静态代码分析。如果在作为 msbuild 一部分的 .NET Core 或 .NET Standard 项目上运行代码分析，则会看到类似“错误: CA0055: 无法确定 <你的 .dll> 的平台”的错误**** 。 若要分析 .NET Core 或 .NET Standard 项目中的代码，请改用 [Roslyn 分析器](../code-quality/roslyn-analyzers-overview.md)。

## <a name="ide-integrated-development-environment-integration"></a>IDE （集成的开发环境） 集成

可以手动或自动在项目上运行代码分析。

若要在每次生成项目时运行代码分析，请在项目的“属性”页上选择“在生成时启用代码分析”****。有关详细信息，请参阅[如何：启用和禁用自动代码分析](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)。

若要在项目上手动运行代码分析，请从菜单栏中选择**分析**>**运行代码分析**>**在 <项目> 上运行代码分析**。

## <a name="rule-sets"></a>规则集

托管代码的代码分析规则可分组为[规则集](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)。可以使用 Microsoft 标准规则集中的一个，也可以根据特定需求[创建自定义规则集](../code-quality/how-to-create-a-custom-rule-set.md)。

## <a name="suppress-warnings"></a>禁止显示警告

通常，指出警告不适用是有用的。这样可以告知开发人员以及可能会在以后检查代码的其他人员：这个警告已被调查过，并且已被禁止显示或被忽略。

在源代码中禁止显示警告是通过自定义特性实现的。 若要禁止显示警告，请向源代码添加特性 `SuppressMessage`，如下面的示例所示：

```csharp
[System.Diagnosis.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]
Public class MyClass
{
   // code
}
```

有关详细信息，请参阅[禁止显示警告](../code-quality/in-source-suppression-overview.md)。

> [!NOTE]
> 如果将项目迁移到 Visual Studio 2017，可能会突然遇到大量代码分析警告。如果还没有准备好修复警告，并且想要立即提高工作效率，则可*重置*项目的分析状态。从**分析**菜单中，选择**运行代码分析并取消未解决的问题**。

## <a name="run-code-analysis-as-part-of-check-in-policy"></a>作为签入策略的一部分运行代码分析

作为组织，你可能希望要求所有签入都满足某些策略。特别是，你希望确保遵循以下策略：

- 签入代码中没有任何生成错误。

- 代码分析作为最新生成的一部分运行。

可以通过指定签入策略来实现该任务。 有关详细信息，请参阅[利用项目签入策略提高代码质量](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)。

## <a name="team-build-integration"></a>Team build 集成

可以使用生成系统的已集成功能在生成过程中运行分析工具。有关详细信息，请参阅 [Azure 管道](/azure/devops/pipelines/index?view=vsts)。

## <a name="see-also"></a>请参阅

- [Roslyn 分析器的概述](../code-quality/roslyn-analyzers-overview.md)
- [使用规则集对代码分析规则进行分组](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [如何：启用和禁用自动代码分析](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)
