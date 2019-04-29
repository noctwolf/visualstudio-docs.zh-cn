---
title: 通过使用旧版 API 自定义代码 Windows |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - code windows
ms.assetid: 5328ab2f-55cb-4680-9744-ec79f55acd1b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c0ea617a252d60d8e8d5810c42f7331508c28165
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62890977"
---
# <a name="customize-code-windows-by-using-the-legacy-api"></a>使用传统的 API 自定义代码窗口
代码窗口是支持一个或多个文本视图的文档窗口对象。 代码窗口的确切功能取决于关联的语言服务。 在多文档界面 (MDI) 模式下，代码窗口是 MDI 子框架。

 代码窗口控制由语言服务，每个语言服务可以提供其自己的代码窗口管理器。 这使语言服务以将其自己修饰添加到代码窗口中，如波形曲线、 着色、 和的详细信息。 有关如何创建核心窗口的详细信息，请参阅[通过使用传统的 API 实例核心编辑器](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)。

 代码窗口是<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame>具有文本视图并确定位置的对象中的任何修饰对象。 语言服务创建时在代码窗口在核心您实例化过程编辑器，可以将附加<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>到代码窗口中，为显示在下图中。

 ![CodeWindow 图](../extensibility/media/vscodewindow.gif "vscodewindow")代码窗口

 语言服务实现代码窗口管理器，并负责管理修饰，如下拉栏。 代码窗口调用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.AddAdornments%2A>在代码窗口初始化过程中的方法。 语言服务时进行此调用时，可以添加下拉栏或按钮栏 (<xref:Microsoft.VisualStudio.TextManager.Interop.IVsButtonBarClient>) 到代码窗口。

## <a name="in-this-section"></a>本节内容
 `Customizing Code Windows by Using the Legacy API` 介绍如何自定义代码窗口使用传统的 API。

- [如何：承载在另一个编辑器中的编辑器](../extensibility/how-to-host-an-editor-in-another-editor.md)说明了如何托管在编辑器窗口内的第二个编辑器。

- [如何：触发事件; 当编辑器失去焦点](../extensibility/how-to-fire-events-when-the-editor-loses-focus.md)介绍了如何将文档视图附加到文档数据对象。

## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>
- <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>
- <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>
- <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>
- [通过使用传统的 API 实例核心编辑器](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)
- [通过使用传统的 API 访问文本视图](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)