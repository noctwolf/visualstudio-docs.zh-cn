---
title: Getting Started with Roslyn 分析器 |Microsoft 文档
ms.date: 04/02/2018
ms.technology: vs-ide-sdk
ms.topic: conceptual
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7b887703343dab10f9cc1f0cbf8e2e2b37b0065b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126804"
---
# <a name="getting-started-with-roslyn-analyzers"></a>入门 Roslyn 分析器

使用 Visual Studio 中的实时、 可基于项目的代码分析器，API 作者可以作为其 NuGet 包的一部分提供特定于域的代码分析。 因为这些分析器由.NET Compiler Platform (代码名为"Roslyn") 提供支持，它们可能会产生警告在代码中的，键入甚至之前已完成的行 （没有更多等待生成你的代码以发现问题）。 分析器也可以出现通过让你立即清理你的代码的 Visual Studio 电灯泡提示自动代码修复。

## <a name="getting-started"></a>入门

[Roslyn 实时代码分析器简介和演练](https://msdn.microsoft.com/magazine/dn879356.aspx)

[添加的代码修复演练： 为分析器的问题提供用户修补程序](https://msdn.microsoft.com/magazine/dn904670.aspx)

[简介和实际分析器 Talk 演练](http://channel9.msdn.com/events/Build/2015/3-725)

[真实世界 Roslyn 分析器](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md)，你也可以观看作为[对话](http://channel9.msdn.com/events/Build/2015/3-725)

[在 github 上，几个示例分为三种类型的分析器](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)

[简介和教程几分析器通信](http://channel9.msdn.com/Events/dotnetConf/2015/NET-Compiler-Platform-Roslyn-Analyzers-and-the-Rise-of-Code-Aware-Libraries)

## <a name="see-also"></a>请参阅

- [Roslyn 分析器概述](../code-quality/roslyn-analyzers-overview.md)
- [在 github OSS 站点上的多个文档](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
- [FxCop 规则实现与 github 上的 Roslyn 分析器](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)