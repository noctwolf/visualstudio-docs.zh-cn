---
title: 包含语言 |Microsoft 文档
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - contained languages
ms.assetid: b75bbb51-8e42-41b1-bece-09ab0b1f03cc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bbf2c63a66ba76b65d1caec2c5eed006d57fca0e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="contained-languages"></a>包含的语言

*包含语言*包含的其他语言的语言。 例如，在 HTML[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]页可能包含[!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]或[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]脚本。 双语言体系结构是必需的.aspx 文件编辑器提供 IntelliSense、 着色、 和其他编辑功能用于 HTML 和脚本语言。

## <a name="implementation"></a>实现

最重要的接口需要实现为包含的语言是<xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage>接口。 任何可以承载在主要语言的语言实现此接口。 它使访问语言服务的着色器、 文本视图筛选器和主要语言服务 id。 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory>使你能够创建<xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage>接口。 以下步骤演示如何实现包含的语言：

1.  使用`QueryService()`若要获取的语言服务 ID 以及的接口 ID <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory>。

2.  若要创建<xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage>界面，请调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory.GetLanguage%2A>方法。 传递<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>接口，一个或多个[项 Id](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID>)，和<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator>接口。

3.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator>接口，该文本缓冲区处理协调器对象，提供了映射到辅助语言的缓冲区中的主文件的位置所需的基本服务。

     例如，在一个.aspx 文件中，主文件将包括 ASP、 HTML 和包含的所有代码。 但是，辅助缓冲区包括以及任何类定义，以使辅助缓冲区成为有效的代码文件仅包含的代码。 缓冲区处理协调器处理的工作的协调一页上的用户对另一个缓冲区上的编辑。

4.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetSpanMappings%2A>方法，这是主要语言，告知缓冲区处理协调器其缓冲区中的哪些文本映射到辅助缓冲区中对应的文本。

     语言将的数组中传递<xref:Microsoft.VisualStudio.TextManager.Interop.NewSpanMapping>结构，当前仅包含一个主和辅助的跨度。

5.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapPrimaryToSecondarySpan%2A>方法和<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapSecondaryToPrimarySpan%2A>方法提供的映射从主到次要缓冲区，反之亦然。