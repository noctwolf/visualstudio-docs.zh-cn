---
title: 如何： 使用并行监视窗口 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.parallelwatch
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, parallel watch window
ms.assetid: 28004d9b-420c-48f7-b80e-ab1519802558
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a5d8354c850d1f55d229ce3f1205ca0bf0fe5f13
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49837069"
---
# <a name="how-to-use-the-parallel-watch-window"></a>如何：使用“并行监视”窗口
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在“并行监视”窗口中，您可同时显示一个表达式保留在多个线程上的值。 每个行均表示一个在应用程序中运行的线程，但一个线程可能用多个行表示。 更具体地说，每个行均表示一个函数调用，其函数签名与当前堆栈帧上的函数的签名匹配。 您可以对列中的项进行排序、重新排序、移除和分组操作。 您可标记、取消标记、冻结（禁止显示）和解冻（恢复）线程。 下面的列会显示在**并行监视**窗口：  
  
- 标记列，可在其中标记要特别注意的线程。  
  
- 帧列，其中箭头指示选定的帧。  
  
- 可配置的列，可显示计算机、进程、平铺、任务和线程。  
  
  > [!TIP]
  >  必须打开**并行任务**窗口中显示中的任务信息**并行监视**窗口。  
  
- **\<添加监视 >** 列中，您可以在其中输入要监视的表达式。  
  
  [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-display-the-parallel-watch-window"></a>显示“并行监视”窗口  
  
1.  在代码中设置断点。  
  
2.  在菜单栏上，依次选择“调试”、“开始调试”。 等待应用程序到达断点。  
  
3.  在菜单栏上依次选择**调试**， **Windows**，**并行监视**，然后选择监视窗口。 您可打开最多 4 个窗口。  
  
### <a name="to-add-a-watch-expression"></a>添加监视表达式  
  
-   选择**\<添加监视 >** ，然后指定监视表达式。  
  
### <a name="to-flag-or-unflag-a-thread"></a>标记或取消标记线程  
  
-   选择标记列的行，或打开线程的快捷菜单并选择**标志**或**取消标记**。  
  
### <a name="to-display-only-flagged-threads"></a>仅显示标记的线程  
  
-   选择仅显示标记按钮的左上角**并行监视**窗口。  
  
### <a name="to-switch-frames"></a>切换帧  
  
-   双击帧列。 （键盘：选择行，然后按 Enter。）  
  
### <a name="to-sort-a-column"></a>为列排序  
  
-   选择列标题。  
  
### <a name="to-group-threads"></a>分组线程  
  
-   打开并行监视窗口的快捷菜单中，选择**Group By**，然后选择相应的子菜单项。  
  
### <a name="to-freeze-or-thaw-threads"></a>冻结或解冻线程  
  
-   打开的行的快捷菜单，然后选择**冻结**或**解冻**。  
  
### <a name="to-export-the-data-in-the-parallel-watch-window"></a>导出“并行监视”窗口中的数据  
  
-   选择**在 Excel 中打开**按钮，然后选择**在 Excel 中打开**或**导出至 CSV**。  
  
### <a name="to-filter-by-a-boolean-expression"></a>按布尔表达式筛选  
  
-   输入中的布尔表达式**按布尔表达式筛选**框。 调试器将为每个线程上下文计算此表达式。 仅显示其中的值为 `true` 的行。  
  
## <a name="see-also"></a>请参阅  
 [调试多线程应用程序](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [如何： 使用 GPU 线程窗口](../debugger/how-to-use-the-gpu-threads-window.md)   
 [演练：调试 C++ AMP 应用程序](http://msdn.microsoft.com/library/40e92ecc-f6ba-411c-960c-b3047b854fb5)



