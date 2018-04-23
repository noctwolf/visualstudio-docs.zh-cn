---
title: 如何： 承载在其他编辑器中的编辑器 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - host a nested editor
ms.assetid: 2b0eb705-fe94-4ca8-93e0-9dbd8ce61a44
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 351d66a9ab9b24c53dac4ed070c80f0e51e5e31f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-host-an-editor-in-another-editor"></a>如何： 承载在其他编辑器中的编辑器
Visual Studio 中可以托管在另一个编辑器，通过指定承载的窗口作为父窗口。 为此，请将参数设置<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2>和<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2>子窗口帧上。  
  
### <a name="to-set-up-the-window-frame-to-host-an-editor"></a>设置窗口框架，以承载编辑器  
  
1.  将编辑器指定为承载的编辑器中，通过创建子窗口窗格。  
  
     此窗格是编辑器的文本的目的地。  
  
2.  创建使用的宿主编辑器<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>或<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenSpecificEditor%2A>方法。  
  
3.  设置<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2>和<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2>中承载的编辑器，通过将这些属性作为参数传递的窗口框架实现的属性<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetProperty%2A>方法，分别。  
  
     如果你需要检索这些参数，将传递到这些属性<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A>方法。  
  
4.  调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A>包含编辑器的方法。  
  
     编辑器将显示在包含编辑器的托管窗格中。  
  
## <a name="robust-programming"></a>可靠编程  
 **应用程序设计器**中的架构师 Visual Studio Team Edition 是承载其他编辑器编辑器窗口框架的示例。 **应用程序设计器**承载在其右侧的窗格中的其他设计器。 设计器面板 (或**属性**页) 的每个包含设计器添加到包含窗口框架。