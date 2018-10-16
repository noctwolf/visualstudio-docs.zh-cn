---
title: 如何： 实现查找和替换机制 |Microsoft Docs
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
- editors [Visual Studio SDK], legacy - find and replace
ms.assetid: bbd348db-3d19-42eb-99a2-3e808528c0ca
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d4ec48a1392efa67f17432f071c9bf4894c35e87
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49304013"
---
# <a name="how-to-implement-the-find-and-replace-mechanism"></a>如何： 实现查找和替换机制
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 提供两种方法来实现查找/替换。 一种方法是将文本图像传递给命令行程序，使其处理，突出显示，具体方法搜索和替换文本。 这样用户就可以指定多个文本段。 或者，你的 VSPackage 可以控制此功能本身。 在这两种情况下，必须通知有关当前的目标和所有打开的文档的目标的 shell。  
  
### <a name="to-implement-findreplace"></a>若要实现查找/替换  
  
1.  实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>接口上的帧属性返回的对象之一<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>或<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>。 如果要创建自定义编辑器，您应实现此接口作为自定义编辑器类的一部分。  
  
2.  使用<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetCapabilities%2A>方法以指定编辑器支持的选项，还可以指示它是否实现了文本图像搜索。  
  
     如果编辑器支持文本图像搜索，实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>。  
  
     否则，实现<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>和<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>。  
  
3.  如果你实现了<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>并<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>方法，可以通过调用简化搜索任务<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper>接口。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>

