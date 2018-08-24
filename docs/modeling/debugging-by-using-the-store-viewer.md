---
title: 使用存储查看器进行调试
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, store viewer
- Domain-Specific Language, store
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: fd0930445ef409f27f87658a249f9c89aac22e91
ms.sourcegitcommit: ef828606e9758c7a42a2f0f777c57b2d39041ac3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "39567059"
---
# <a name="debugging-by-using-the-store-viewer"></a>使用存储查看器进行调试
使用存储查看器中，可以检查的状态*存储*由[!INCLUDE[dsl](../modeling/includes/dsl_md.md)]。 存储查看器显示所有在元素属性的元素之间的链接以及特定商店中的域模型元素。

## <a name="opening-store-viewer"></a>打开存储查看器
 当你处于[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]实验性生成，请停止在断点处代码在其中存储的实例包含模型的信息。 然后，通过键入以下命令中的打开存储查看器**即时**窗口：

```csharp
Microsoft.VisualStudio.Modeling.Diagnostics.StoreViewer.Show(mystore);
```

> [!NOTE]
>  必须将为`mystore`与存储实例的名称。 此外，如果将命名空间添加到你的代码，您可以键入用于显示存储查看器，而无需完全限定的命名空间命令：
>
>  `using Microsoft.VisualStudio.Modeling.Diagnostics;`
>
>  `...`
>
>  `StoreViewer.Show(mystore);`

 `Show`方法有若干重载。 可以作为参数来指定应用商店或分区的实例。

 或者，可以放置的任何位置可存储查看器显示代码中的代码行的参数传递给`Show`方法处于范围。 当作为存储的内容的快照执行的代码行时，此操作将显示存储查看器。

### <a name="using-store-viewer"></a>使用存储查看器
 存储查看器打开后，无模式 Windows 窗体窗口出现，如下图所示。

 ![](../modeling/media/storeviewer2.png) 存储查看器

 存储查看器有三个窗格： 右上方窗格中，左窗格中，右下方的窗格。 左窗格中是树视图中的类型的`DomainDataDirectory`存储区的成员。 如果您展开分区节点，并单击一个元素，在右上方窗格中显示元素的属性。 如果元素链接到其他元素，右下方窗格中显示的其他元素。 如果您双击右下方窗格中的元素，该元素的左窗格中突出显示。

## <a name="see-also"></a>请参阅

- [在程序代码中导航和更新模型](../modeling/navigating-and-updating-a-model-in-program-code.md)