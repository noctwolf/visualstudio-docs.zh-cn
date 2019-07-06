---
title: 开始使用 Roslyn 分析器 |Microsoft Docs
ms.date: 04/02/2018
ms.topic: conceptual
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d6a6f4123f72afd8c310e627a9da6759f4c4548a
ms.sourcegitcommit: 32144a09ed46e7223ef7dcab647a9f73afa2dd55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/05/2019
ms.locfileid: "67586960"
---
# <a name="get-started-with-roslyn-analyzers"></a>开始使用 Roslyn 分析器

通过在 Visual Studio 中的实时、 基于项目的代码分析器，API 作者可以提供特定于域的代码分析作为其 NuGet 包的一部分。 这些分析器由.NET 编译器平台 (代号为"Roslyn") 提供支持，因为它们可能会产生警告在代码中的，键入即使之前已完成 （不再等到生成代码以便发现问题） 的行。 分析器还可能会出现通过 Visual Studio 灯泡图标提示来让您立即清理代码的自动代码修补程序。

## <a name="get-started"></a>入门

[Roslyn 分析器概述](../code-quality/roslyn-analyzers-overview.md)

[教程：编写第一个分析器和代码修补程序](/dotnet/csharp/roslyn-sdk/tutorials/how-to-write-csharp-analyzer-code-fix)

[添加代码修补程序演练：分析器问题提供用户的修补程序](https://msdn.microsoft.com/magazine/dn904670.aspx)

[现实世界 Roslyn 分析器](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md)，还可查看作为[通信](https://channel9.msdn.com/events/Build/2015/3-725)

[GitHub 上的几个示例分为三种类型的分析器](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)

## <a name="see-also"></a>请参阅

- [.NET 编译器平台包版本参考](roslyn-version-support.md)
- [GitHub OSS 站点上的多个文档](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)
- [FxCop 规则实现通过 Roslyn 分析器](http://roslynanalyzersstatus.azurewebsites.net/)
