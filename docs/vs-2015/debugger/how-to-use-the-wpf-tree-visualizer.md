---
title: 如何： 使用 WPF 树可视化工具 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- WPF, debugging
- debugging, WPF
ms.assetid: 2a1bf1cd-90f9-4d06-9fb4-1bfc925afef3
caps.latest.revision: 21
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 69ce98efe7429b011915f14b267cf5346528a93d
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51752109"
---
# <a name="how-to-use-the-wpf-tree-visualizer"></a>如何：使用 WPF 树可视化工具
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

可以使用 WPF 树可视化工具浏览 WPF 对象的可视化树，并查看该树中所含对象的 WPF 依赖项属性。 有关可视化树的详细信息，请参阅[WPF 中的树](http://msdn.microsoft.com/library/e83f25e5-d66b-4fc7-92d2-50130c9a6649)。 有关依赖项属性的详细信息，请参阅[依赖属性概述](http://msdn.microsoft.com/library/d119d00c-3afb-48d6-87a0-c4da4f83dee5)。  
  
 当您打开 WPF 树可视化工具时，您将看到两个窗格：**可视化树**左侧并**的属性**_名称_**:** _类型_右侧窗格中的。 选择中的任何对象**可视化树**窗格中，并**的属性**_名称_**:**_类型_窗格自动更新为显示该对象的属性。  
  
### <a name="to-open-the-wpf-tree-visualizer"></a>打开 WPF 树可视化工具  
  
1.  在数据提示中， **Watch**窗口中，**自动**窗口中，或**局部变量**窗口中的，WPF 对象名称旁单击放大镜图标旁的箭头。  
  
     将会显示可视化工具列表。  
  
2.  单击**WPF 树可视化工具**。  
  
### <a name="to-search-the-visual-tree"></a>搜索可视化树  
  
-   在中**可视化树**窗格中，键入你想要在中搜索的字符串**搜索**框。  
  
     WPF 树可视化工具将立即在可视化树中查找与你键入的字符串匹配的第一个对象。 键入更多字符可找到更精确的匹配项。  
  
    -   若要转到下一个匹配项的可视化树中，单击**下一步**。  
  
    -   若要返回到上一个匹配项，请单击**Prev**。  
  
    -   若要清除搜索条件，请单击**清除**。  
  
### <a name="to-search-the-properties-list"></a>搜索属性列表  
  
-   在中**的属性**_名称_**:**_类型_窗格中，键入你想要在中搜索的字符串**筛选**框。  
  
     WPF 树可视化工具将立即查找与你键入的字符串匹配的属性；现在，列表中仅显示与键入的字符串匹配的那些属性。 键入更多字符可找到更精确的匹配项。  
  
    -   若要清除搜索条件，请单击**清除**。  
  
### <a name="to-close-the-visualizer"></a>关闭可视化工具  
  
-   单击**关闭**右上角的对话框的图标。  
  
## <a name="see-also"></a>请参阅  
 [如何： 使用可视化工具](../misc/how-to-use-a-visualizer.md)   
 [创建自定义可视化工具](../debugger/create-custom-visualizers-of-data.md)   
 [WPF 中的树](http://msdn.microsoft.com/library/e83f25e5-d66b-4fc7-92d2-50130c9a6649)   
 [依赖项属性概述](http://msdn.microsoft.com/library/d119d00c-3afb-48d6-87a0-c4da4f83dee5)



