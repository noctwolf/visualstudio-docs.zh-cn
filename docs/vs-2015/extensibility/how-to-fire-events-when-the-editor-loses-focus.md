---
title: 如何： 触发事件; 当编辑器失去焦点 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
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
ms.openlocfilehash: 2462e41470b72c63f5c96a69d2776af2a640c372
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477171"
---
# <a name="how-to-fire-events-when-the-editor-loses-focus"></a>如何： 触发事件; 当编辑器失去焦点
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 触发事件时编辑器失去焦点](https://docs.microsoft.com/visualstudio/extensibility/how-to-fire-events-when-the-editor-loses-focus)。  
  
有时有必要知道当编辑器失去焦点的窗口框架上。 例如，可能需要在代码窗口中提取代码后对其焦点不再位于编辑器中。 以下过程提供了为接收通知的编辑器失去焦点要遵循的步骤。  
  
### <a name="to-fire-an-event-in-response-to-an-editor-losing-focus"></a>触发事件以响应编辑器失去焦点  
  
1.  通过获取监视所选内容的事件<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>对象从<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>。  
  
2.  调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.AdviseSelectionEvents%2A>并将其提供你<xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents>对象。  
  
3.  在调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A>，查找`elementid==SEID_WindowFrame`。  
  
4.  测试`varValueNew`两个参数：  
  
    1.  要查找该窗口框架。  
  
    2.  您的程序会失去对该窗口框架的选择点。

