---
title: 如何： 实现查找和替换机制 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - find and replace
ms.assetid: bbd348db-3d19-42eb-99a2-3e808528c0ca
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 26d1866d9b816dfca3f82f98db372865f9d27a68
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128932"
---
# <a name="how-to-implement-the-find-and-replace-mechanism"></a>如何： 实现查找和替换机制
Visual Studio 提供两种方法来实现查找/替换。 一种方法是将文本图像传递给命令行界面，并让它处理搜索、 突出显示，以及替换文本。 这样用户就可以指定多个文本范围。 或者，你的 VSPackage 可以控制此功能本身。 在这两种情况下必须通知有关的当前目标和所有打开的文档的目标 shell。  
  
### <a name="to-implement-findreplace"></a>若要实现查找/替换  
  
1.  实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>框架属性返回的对象之一上的接口<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>或<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>。 如果要创建自定义编辑器，则应实现此接口作为自定义编辑器类的一部分。  
  
2.  使用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetCapabilities%2A>方法来指定你的编辑器支持的选项，还可以指示是否实现文本映像搜索。  
  
     如果你的编辑器支持文本映像搜索，实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>。  
  
     否则，实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>和<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>。  
  
3.  如果你实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>和<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>方法，你可以通过调用来简化你搜索的任务<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper>接口。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>