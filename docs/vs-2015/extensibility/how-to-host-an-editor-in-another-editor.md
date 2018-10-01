---
title: 如何： 承载在另一个编辑器中的编辑器 |Microsoft Docs
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
- editors [Visual Studio SDK], legacy - host a nested editor
ms.assetid: 2b0eb705-fe94-4ca8-93e0-9dbd8ce61a44
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6390f5550c445239fbd8f8f72f9c8c4ad013665a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471680"
---
# <a name="how-to-host-an-editor-in-another-editor"></a>如何： 承载的编辑器中另一个编辑器
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 在其他编辑器中的主机编辑器](https://docs.microsoft.com/visualstudio/extensibility/how-to-host-an-editor-in-another-editor)。  
  
在 Visual Studio 中可以通过指定为父窗口的承载窗口托管在另一个编辑器。 若要执行此操作，设置参数<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2>和<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2>上子窗口框架。  
  
### <a name="to-set-up-the-window-frame-to-host-an-editor"></a>若要设置窗口框架来托管编辑器  
  
1.  将编辑器指定为承载编辑器中，通过创建子窗口窗格。  
  
     此窗格是将在哪里编辑器的文本。  
  
2.  创建使用托管编辑器<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>或<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenSpecificEditor%2A>方法。  
  
3.  设置<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2>并<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2>中通过将这些属性作为参数传递的承载编辑器的窗口框架实现的属性<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetProperty%2A>方法，分别。  
  
     如果需要检索这些参数，请将传递到这些属性<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A>方法。  
  
4.  调用<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A>包含编辑器的方法。  
  
     在编辑器中包含编辑器的托管窗格中显示。  
  
## <a name="robust-programming"></a>可靠编程  
 **应用程序设计器**在面向架构师的 Visual Studio Team Edition 是托管另一个编辑器的编辑器窗口框架的一个示例。 **应用程序设计器**承载在其右侧窗格中的其他设计器。 设计器面板 (或**属性**页) 对于每个包含设计器添加到包含窗口框架。

