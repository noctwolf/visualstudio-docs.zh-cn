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

Visual Studio 2017 分析托管的代码通过两种方式： 使用旧版*FxCop*静态分析托管程序集，并使用.NET 编译器平台*分析器*。 本主题介绍 FxCop 静态代码分析。 若要了解有关使用.NET Compiler Platform 分析器来分析代码的详细信息，请参阅[概述的 Roslyn 分析器](../code-quality/roslyn-analyzers-overview.md)。

针对托管代码的代码分析用于分析托管程序集并报告有关程序集的信息，例如 Microsoft .NET Framework 设计准则中规定的编程和设计规则的冲突。

分析工具将它在分析期间执行的检查表示为警告消息。 警告消息标识任何相关的编程和设计问题，如有可能，还提供有关如何修复问题的信息。

> [!NOTE]
> 在 Visual Studio 中的.NET Core 和.NET Standard 项目不支持静态代码分析。 如果 msbuild 的一部分，可以对.NET Core 或.NET Standard 项目运行代码分析，您将看到类似的错误**错误： CA0055： 无法识别平台\<your.dll >**。 若要分析.NET Core 或.NET Standard 项目中的代码，使用[Roslyn 分析器](../code-quality/roslyn-analyzers-overview.md)相反。

## <a name="ide-integrated-development-environment-integration"></a>IDE （集成的开发环境） 集成

手动或自动，可以对你的项目中运行代码分析。

若要生成项目时每次运行代码分析，请选择**生成时启用代码分析**项目的属性页上。 有关详细信息，请参阅[如何： 启用和禁用自动代码分析](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)。

若要对项目手动运行代码分析，在菜单栏上选择**分析** > **运行代码分析** > **上运行代码分析\<项目>**。

## <a name="rule-sets"></a>规则集

托管代码的代码分析规则分为[规则集](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)。 可以使用一个 Microsoft 标准规则集，也可以[创建自定义规则集](../code-quality/how-to-create-a-custom-rule-set.md)以满足特定需求。

## <a name="suppress-warnings"></a>禁止显示警告

它通常用于指示警告不适用。 这样，便可以通知开发人员以及可能会在以后检查代码的其他人员：已调查了一个警告，且禁止显示或忽略了该警告。

在源中的禁止显示警告是通过自定义特性实现的。 若要禁止显示警告，请向源代码添加特性 `SuppressMessage`，如下面的示例所示：

```csharp
[System.Diagnosis.CodeAnalysis.SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]
Public class MyClass
{
   // code
}
```

有关详细信息，请参阅[禁止显示警告](../code-quality/in-source-suppression-overview.md)。

> [!NOTE]
> 如果将项目迁移到 Visual Studio 2017 时，可能会突然遇到具有大量代码分析警告。 如果您不准备好修复警告，并且想要立即提高工作效率，你可以*基线*你的项目的分析状态。 从**分析**菜单中，选择**运行代码分析并取消未解决的问题**。

## <a name="run-code-analysis-as-part-of-check-in-policy"></a>作为签入策略的一部分运行代码分析

作为一个单位，可能希望所有签入行为满足特定的策略。 特别是希望确保遵从下列策略：

- 签入代码中没有任何生成错误。

- 作为最新生成的一部分运行代码分析。

可以通过指定签入策略来实现该任务。 有关详细信息，请参阅[利用项目签入策略提高代码质量](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)。

## <a name="team-build-integration"></a>Team build 集成

你可以使用生成系统的集成功能在生成过程中运行分析工具。 有关详细信息，请参阅[Azure 管道](/azure/devops/pipelines/index?view=vsts)。

## <a name="see-also"></a>请参阅

- [Roslyn 分析器的概述](../code-quality/roslyn-analyzers-overview.md)
- [使用规则集对代码分析规则进行分组](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)
- [如何：启用和禁用自动代码分析](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)
