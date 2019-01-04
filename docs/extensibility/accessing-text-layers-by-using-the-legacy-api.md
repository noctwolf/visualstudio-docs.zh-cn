---
title: 使用旧版 API 访问文本层 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - text layers
ms.assetid: 2258fcdd-38d1-479d-b8f8-1d4e6525f72c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 47085216c6f20ca1add535a76ce4f5fb4043a6dd
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53945933"
---
# <a name="access-text-layers-by-using-the-legacy-api"></a>通过使用传统的 API 访问文本层
文本层通常封装文本布局的某些方面。 例如，"函数--一次"层隐藏文本之前和之后包含脱字号 （文本插入点） 的函数。  
  
 文本层驻留缓冲区和视图之间，并且它会修改该视图可以看到缓冲区的内容的方式。  
  
## <a name="text-layer-information"></a>文本层信息  
 以下列表描述了文本层中的工作原理[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]:  
  
-   文本层中的文本可以均带有语法着色和标记。  
  
-   当前不能实现您自己的层。  
  
-   一个层公开<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>，它派生自<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>。 文本缓冲区本身也作为一个层，就能够查看处理以多态形式使用基础层实现。  
  
-   在视图和缓冲区之间可能存在任意数目的层。 每个层仅处理它，下面的层和视图很大程度上处理的最顶层的层。 （视图中确实必须将缓冲区的一些信息。）  
  
-   一个层可能会影响其下面的层。 它不会影响源自标准事件超出其上方层。  
  
-   在编辑器中，隐藏的文本、 综合文本和自动换行作为层实现。 不直接与层交互的情况下，可以实现隐藏和合成的文本。 有关详细信息，请参阅[旧版语言服务中的大纲显示](../extensibility/internals/outlining-in-a-legacy-language-service.md)和<xref:Microsoft.VisualStudio.TextManager.Interop.IVsSyntheticTextSession>。  
  
-   每个文本层都有其自己本地的坐标系统，通过公开<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>接口。 行包装层，例如，可能包含两行，而基础的文本缓冲区可能包含只有一行。  
  
-   视图层通过与通信<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView>接口。 使用此接口来协调缓冲区坐标视图坐标。  
  
-   任何层如源自文本的综合文本层必须提供的本地实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CreateTrackingPoint%2A>。  
  
-   除了<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>，必须实现文本层<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>触发中的事件和<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents>接口。  
  
## <a name="see-also"></a>请参阅  
 [自定义编辑器中的语法着色](../extensibility/syntax-coloring-in-custom-editors.md)   
 [文本标记中使用传统的 API](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [使用传统的 API 自定义编辑器控件和菜单](../extensibility/customizing-editor-controls-and-menus-by-using-the-legacy-api.md)