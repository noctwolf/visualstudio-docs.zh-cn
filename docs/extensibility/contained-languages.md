---
title: 包含语言 |Microsoft Docs
ms.date: 03/22/2018
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - contained languages
ms.assetid: b75bbb51-8e42-41b1-bece-09ab0b1f03cc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ce2079ce16ac339ae536430d02d546ea39ffae0a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53873997"
---
# <a name="contained-languages"></a>包含的语言

*包含语言*是所包含的其他语言的语言。 例如，在 HTML[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]可能包含页[!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]或[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]脚本。 双语言体系结构所需 *.aspx*文件编辑器提供 IntelliSense、 着色、 和其他编辑功能的 HTML 和脚本语言。

## <a name="implementation"></a>实现

您需要实现包含语言的最重要的接口是<xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage>接口。 此接口实现的任何语言都可以承载于主要语言内。 它允许访问语言服务的着色器、 文本视图筛选器和主要语言服务 id。 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory>使您能够创建<xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage>接口。 以下步骤演示如何实现包含的语言：

1.  使用`QueryService()`以获取语言服务 ID 和的接口 ID <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory>。

2.  若要创建<xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage>接口，请调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory.GetLanguage%2A>方法。 传递<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>接口，一个或多个[项 Id](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID>)，和一个<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator>接口。

3.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator>接口，这是文本缓冲区处理协调器对象，提供了将映射到辅助语言的缓冲区中主文件的位置所需的基本服务。

     例如，在单个 *.aspx*文件中，主文件包括 ASP、 HTML 和包含的所有代码。 但是，辅助缓冲区包含以及任何类定义，以使辅助缓冲区有效的代码文件仅包含的代码。 缓冲区处理协调器处理的协调对另一个缓冲区中的编辑的工作。

4.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetSpanMappings%2A>方法，它是主要语言，指示缓冲区处理协调器什么文本内其缓冲区映射到辅助缓冲区中的相应文本。

     该语言将在一个数组中传递<xref:Microsoft.VisualStudio.TextManager.Interop.NewSpanMapping>结构当前只包括一个主证书和辅助跨度。

5.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapPrimaryToSecondarySpan%2A>方法和<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapSecondaryToPrimarySpan%2A>方法提供的映射从主数据库到辅助缓冲区，反之亦然。