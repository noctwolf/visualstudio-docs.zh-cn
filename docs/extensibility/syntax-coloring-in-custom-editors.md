---
title: 语法着色中自定义编辑器 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - syntax coloring
ms.assetid: 74900b9a-baef-432a-8231-4568fb5e19ad
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 18e087e82754244b7abda530f733a6047447f4a7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31139456"
---
# <a name="syntax-coloring-in-custom-editors"></a>语法着色中自定义编辑器
Visual Studio 环境 SDK 编辑器，包括核心编辑器中，使用语言服务标识特定的语法项并将它们显示具有给定的文档视图的指定颜色。

## <a name="colorization-requirements"></a>着色要求
 必须实现语言服务的着色器的所有编辑器：

1.  使用一个对象，实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>来管理要被着色的文本和一个对象，实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>以提供文本的文档视图。

2.  通过查询使用语言服务的标识 GUID 的 VSPackage 的服务提供程序来获取特定语言服务的接口。

3.  调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer.SetLanguageServiceID%2A>方法的对象实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>。 此方法将关联的语言服务<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>VSPackage 使用来管理是被着色的文本的实现。

## <a name="core-editor-usage-of-a-language-services-colorizer"></a>核心编辑器的语言服务的着色器的使用情况
 核心编辑器、 分析和呈现的文本由语言服务的着色器的实例时获取具有着色器的语言服务将自动进行而不需要您采取任何进一步的干预。

 IDE 以透明方式：

-   调用着色器根据需要用于分析和分析文本，因为它正在添加或修改的实现中<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer>。

-   确保提供的提供的文档视图显示<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>实现将更新和重新绘制使用着色器返回的信息。

## <a name="non-core-editor-usage-of-a-language-services-colorizer"></a>语言服务的着色器的非核心编辑器使用情况
 非核心编辑器实例还可以使用语言服务的语法着色服务，但它们必须显式检索和应用服务的着色器和重绘其自身的文档视图。

 若要执行此操作，非核心编辑器必须：

1.  获取语言服务的着色器对象 (可实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer>和<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer2>)。 VSPackage 将这是通过调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer%2A>语言服务的接口上的方法。

2.  调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>方法来请求特定的一段文本被着色。

     <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>方法返回的值的数组，一个用于在文本中的每个字母跨越着色。 它还标识为特定类型的着色的项，例如注释、 关键字或数据类型的文本范围。

3.  使用返回的着色信息<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>重绘并显示其文本。

> [!NOTE]
> 除了使用语言服务的着色器，VSPackage 可以选择使用通用的 Visual Studio 环境 SDK 文本着色机制。 此机制的详细信息，请参阅[使用字体和颜色](../extensibility/using-fonts-and-colors.md)。

## <a name="see-also"></a>另请参阅

- [在旧版语言服务中进行语法着色](../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)
- [实现语法着色](../extensibility/internals/implementing-syntax-coloring.md)
- [如何：使用内置的可着色项](../extensibility/internals/how-to-use-built-in-colorable-items.md)
- [自定义可着色项](../extensibility/internals/custom-colorable-items.md)