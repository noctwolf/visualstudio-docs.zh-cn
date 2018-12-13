---
title: 如何： 触发事件; 当编辑器失去焦点 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - fire events on losing focus
ms.assetid: 64d40695-6917-468a-8037-a253453ac159
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2875ff13302b1f54d87f1f69a68757b10fb98dca
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51749224"
---
# <a name="how-to-fire-events-when-the-editor-loses-focus"></a>如何： 触发事件; 当编辑器失去焦点
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

有时有必要知道当编辑器失去焦点的窗口框架上。 例如，可能需要在代码窗口中提取代码后对其焦点不再位于编辑器中。 以下过程提供了为接收通知的编辑器失去焦点要遵循的步骤。  
  
### <a name="to-fire-an-event-in-response-to-an-editor-losing-focus"></a>触发事件以响应编辑器失去焦点  
  
1.  通过获取监视所选内容的事件<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>对象从<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>。  
  
2.  调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.AdviseSelectionEvents%2A>并将其提供你<xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents>对象。  
  
3.  在调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A>，查找`elementid==SEID_WindowFrame`。  
  
4.  测试`varValueNew`两个参数：  
  
    1.  要查找该窗口框架。  
  
    2.  您的程序会失去对该窗口框架的选择点。

