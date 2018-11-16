---
title: 开始使用 Roslyn 分析器 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 367c2ec8-3059-46a5-9d1c-57bead0419e7
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5c90744c8cba05858a231dd60ec447979a76edb7
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51774778"
---
# <a name="getting-started-with-roslyn-analyzers"></a>Roslyn 分析器入门
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

通过在 Visual Studio 中的实时、 基于项目的代码分析器，API 作者可以提供特定于域的代码分析作为其 NuGet 包的一部分。  这些分析器由.NET 编译器平台 (代号为"Roslyn") 提供支持，因为它们可能会产生警告在代码中的，键入即使之前已完成 （不再等到生成代码以便发现问题） 的行。  分析器，还可能会出现通过 Visual Studio 灯泡图标提示来让您立即清理代码的自动代码修补程序  
  
## <a name="getting-started"></a>入门  
 [Roslyn 实时代码分析器说明和演练](https://msdn.microsoft.com/magazine/dn879356.aspx)  
  
 [添加代码修补程序的演练： 为分析器问题提供用户的修补程序](https://msdn.microsoft.com/magazine/dn904670.aspx)  
  
 [说明和演练的现实世界分析器讨论](http://channel9.msdn.com/events/Build/2015/3-725)  
  
 [真实世界 Roslyn 分析器](../extensibility/roslyn-analyzers-and-code-aware-library-for-immutablearrays.md)，还可查看作为[通信](http://channel9.msdn.com/events/Build/2015/3-725)  
  
 [Github 上的几个示例分为三种类型的分析器](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Analyzer%20Samples.md)  
  
 [简介和教程的几个分析器通信](http://channel9.msdn.com/Events/dotnetConf/2015/NET-Compiler-Platform-Roslyn-Analyzers-and-the-Rise-of-Code-Aware-Libraries)  
  
## <a name="other-resources"></a>其他资源  
 [Github OSS 站点上的多个文档](https://github.com/dotnet/roslyn/tree/master/docs/analyzers)  
  
 [FxCop 规则实现通过 github 上的 Roslyn 分析器](https://github.com/dotnet/roslyn/tree/master/src/Diagnostics/FxCop)

