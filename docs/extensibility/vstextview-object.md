---
title: VSTextView 对象 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VSTextView
helpviewer_keywords:
- VSTextView object, reference
- views [Visual Studio SDK], reference
ms.assetid: 78272ddc-9718-4c65-a94e-a44a2e8d54f4
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eddd5640b2f8f073f791f6bdb4dc006f8fab0e36
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "66322816"
---
# <a name="vstextview-object"></a>VSTextView 对象
文本视图是一个窗口，允许用户查看和编辑文本缓冲区的 Unicode 文本。 实际上，该视图是大多数用户的编辑器的参考。 视图从缓冲区由各种文本层 （自动换行、 大纲显示文本等） 分开的因为视图不保证可精确地表示缓冲区中的文本。 有关文本视图的详细信息，请参阅[使用传统的 API 访问文本视图](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)

 下表显示了中的接口<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>对象。

|接口|描述|
|---------------|-----------------|
|[IDropSource](/windows/desktop/api/oleidl/nn-oleidl-idropsource)|标准 OLE 接口。|
|<xref:Microsoft.VisualStudio.OLE.Interop.IDropTarget>|标准 OLE 接口。|
|<xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite>|标准 OLE 接口。|
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|标准 OLE 接口。|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|可以创建复合操作 （即，在撤消/重做单个单元进行分组的操作）。|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|提供用于管理和访问视图基本方法。 `IVsTextView` 没有经过线程安全。|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|创建和管理窗口窗格。|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView>|与文本层进行交互。|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsThreadSafeTextView>|从不同的线程执行在视图上的操作。|

## <a name="see-also"></a>请参阅
- [图编辑](https://www.microsoft.com/download/details.aspx?id=55984)
- [VSTextBuffer 对象](../extensibility/vstextbuffer-object.md)
- [通过使用传统的 API 访问文本视图](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)