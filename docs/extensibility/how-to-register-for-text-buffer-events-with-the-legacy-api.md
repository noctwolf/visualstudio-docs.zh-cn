---
title: 如何：为使用旧 API 的文本缓冲区事件注册 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - register for text buffer events
ms.assetid: 5fc00ced-882c-4b48-b46c-1fa5a2469f94
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8ec5c271c023483ea64ddbabb83129ea9a44e4c2
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60052749"
---
# <a name="how-to-register-for-text-buffer-events-with-the-legacy-api"></a>如何：注册文本缓冲区事件与传统的 API
如果使用传统的 API 来访问文本缓冲区，则应注册文本缓冲区事件，如下面的过程中所示。

## <a name="to-advise-text-buffer-events"></a>若要向建议文本缓冲区事件

1. 从指向上的接口之一<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>，调用`QueryInterface`指向的指针为<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>。

2. 调用<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer.FindConnectionPoint%2A>方法，并传入你想要注册的事件的接口 ID。

     例如，如果你想要注册，以便<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents>，然后在一个接口 ID 的 IID_IVsTextLinesEvents 中传递。

     文本缓冲区返回一个指向<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint>适当的连接点对象的接口。

3. 使用此指针，调用<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Advise%2A>方法，传入指向您想要为其注册，例如，事件接口的实现`IVsTextLinesEvents`接口。

     该环境将返回的 cookie，您可以使用它来停止侦听事件通过调用<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Unadvise%2A>方法。

## <a name="see-also"></a>请参阅
- [传统的 API 中的文本缓冲区事件](../extensibility/text-buffer-events-in-the-legacy-api.md)