---
title: 如何： 为与旧版 API 的文本缓冲区事件注册 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - register for text buffer events
ms.assetid: 5fc00ced-882c-4b48-b46c-1fa5a2469f94
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b708507096e7035039e54af7505c8f5f939b5724
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-register-for-text-buffer-events-with-the-legacy-api"></a>如何： 为与旧版 API 的文本缓冲区事件注册
如果要通过使用旧的 API 来访问文本缓冲区，你应该注册文本缓冲区事件按下列步骤中所示。  
  
### <a name="to-advise-text-buffer-events"></a>向建议文本缓冲区事件  
  
1.  从指向上的接口之一<xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>，调用`QueryInterface`为指向的<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer>。  
  
2.  调用<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer.FindConnectionPoint%2A>方法，并传入你想要注册的事件的接口 ID。  
  
     例如，如果你想要注册<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents>，然后将接口 ID 的 IID_IVsTextLinesEvents 中传递。  
  
     文本缓冲区返回到指针<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint>适当的连接点对象的接口。  
  
3.  使用此指针，调用<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Advise%2A>方法，在一个指针将传递给你想要为其注册，例如，事件接口的实现`IVsTextLinesEvents`接口。  
  
     该环境将返回一个 cookie，然后，可以使用，来停止侦听事件通过调用<xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPoint.Unadvise%2A>方法。  
  
## <a name="see-also"></a>另请参阅  
 [旧版 API 中的文本缓冲区事件](../extensibility/text-buffer-events-in-the-legacy-api.md)