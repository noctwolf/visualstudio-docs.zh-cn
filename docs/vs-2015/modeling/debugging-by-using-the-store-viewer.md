---
title: 使用存储查看器进行调试 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, store viewer
- Domain-Specific Language, store
ms.assetid: 0178db2e-ae99-4ed3-9b87-8620fa9fa8e4
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 62425e6144e11f32d6933f134291fab01a15e6c3
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58934656"
---
# <a name="debugging-by-using-the-store-viewer"></a>使用存储查看器进行调试
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

使用存储查看器中，可以检查的状态*存储*由[!INCLUDE[dsl](../includes/dsl-md.md)]。 存储查看器显示所有在元素属性的元素之间的链接以及特定商店中的域模型元素。  
  
## <a name="opening-store-viewer"></a>打开存储查看器  
 当你处于[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]实验性生成，请停止在断点处代码在其中存储的实例包含模型的信息。 然后，通过键入以下命令中的打开存储查看器**即时**窗口：  
  
```  
Microsoft.VisualStudio.Modeling.Diagnostics.StoreViewer.Show(mystore);  
```  
  
> [!NOTE]
>  必须将为`mystore`与存储实例的名称。 此外，如果将命名空间添加到你的代码，您可以键入用于显示存储查看器，而无需完全限定的命名空间命令：  
>   
>  `using Microsoft.VisualStudio.Modeling.Diagnostics;`  
>   
>  `…`  
>   
>  `StoreViewer.Show(mystore);`  
  
 `Show`方法有若干重载。 可以作为参数来指定应用商店或分区的实例。  
  
 或者，可以放置的任何位置可存储查看器显示代码中的代码行的参数传递给`Show`方法处于范围。 当作为存储的内容的快照执行的代码行时，此操作将显示存储查看器。  
  
### <a name="using-store-viewer"></a>使用存储查看器  
 存储查看器打开后，无模式 Windows 窗体窗口出现，如下图所示。  
  
 ![](../modeling/media/storeviewer2.png "storeviewer2")  
存储查看器  
  
 存储查看器有三个窗格： 右上方窗格中，左窗格中，右下方的窗格。 左窗格中是树视图中的类型的`DomainDataDirectory`存储区的成员。 如果您展开分区节点，并单击一个元素，在右上方窗格中显示元素的属性。 如果元素链接到其他元素，右下方窗格中显示的其他元素。 如果您双击右下方窗格中的元素，该元素的左窗格中突出显示。  
  
## <a name="see-also"></a>请参阅  
 [在程序代码中导航和更新模型](../modeling/navigating-and-updating-a-model-in-program-code.md)
