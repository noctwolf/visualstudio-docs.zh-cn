---
title: 如何： 触发事件; 当编辑器失去焦点 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - fire events on losing focus
ms.assetid: 64d40695-6917-468a-8037-a253453ac159
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bbdcf30443bc548fd8d182db301cbc7119d8ceae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-fire-events-when-the-editor-loses-focus"></a>如何： 触发事件; 当编辑器失去焦点
有时很必要知道当编辑器失去焦点的窗口帧上。 例如，你可能需要从代码窗口提取代码后在它不再聚焦于编辑器。 以下过程提供为接收通知的失去焦点的编辑器要遵循的步骤。  
  
### <a name="to-fire-an-event-in-response-to-an-editor-losing-focus"></a>若要触发事件以响应编辑器失去焦点  
  
1.  通过获取监视选择事件<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>对象<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>。  
  
2.  调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.AdviseSelectionEvents%2A>并将其提供你<xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents>对象。  
  
3.  调用中<xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A>，查找`elementid==SEID_WindowFrame`。  
  
4.  测试`varValueNew`两项操作的参数：  
  
    1.  您正在寻找窗口框架。  
  
    2.  从该处程序失去选定范围向该窗口框架的点。