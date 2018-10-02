---
title: 如何： 搜索在 Windows 视图窗口 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- windows, searching in Windows view
ms.assetid: 30306970-b861-4315-acf8-f86a43d4e73b
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 043e3e92004eb5b0995bc285e90a138f4dc902f4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479964"
---
# <a name="how-to-search-for-a-window-in-windows-view"></a>如何：在窗口视图中搜索窗口
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 搜索在 Windows 视图窗口](https://docs.microsoft.com/visualstudio/debugger/how-to-search-for-a-window-in-windows-view)。  
  
您可以使用其句柄、 标题、 类或其标题和类的组合作为搜索条件搜索 Windows 视图中的特定窗口。 此外可以指定搜索的初始传递方向。 在对话框中的字段将窗口树中显示所选的窗口的属性。  
  
 开头到第二个级别 (所有 windows 桌面的子级)，展开树，以便可以确定由其类名称和标题的桌面级别 windows。 一旦您选择了一个桌面级别窗口，您可以展开该级别以查找特定子窗口。  
  
### <a name="to-search-for-a-window-in-windows-view"></a>若要搜索在 Windows 视图窗口  
  
1.  排列窗口，因此该 Spy + + 中， [Windows 视图](../debugger/windows-view.md)窗口和目标窗口中都可见。  
  
2.  从**搜索**菜单中，选择**查找窗口**。  
  
     [窗口搜索对话框](../debugger/window-search-dialog-box.md)随即打开。  
  
    > [!TIP]
    >  若要减少屏幕混乱，请选择**隐藏 Spy**选项。 此选项将隐藏 Spy + + 主窗口，仅留下**窗口搜索**对话框显示在其他应用程序的前面。 Spy + + 主窗口将还原时，单击**确定**或**取消**，或如果清除**隐藏 Spy + +** 选项。  
  
3.  拖动**查找程序工具**通过目标窗口。 拖动该工具中，**窗口搜索**对话框显示有关所选的窗口的详细信息。  
  
     - 或 -  
  
     如果您知道所需的窗口的句柄 （例如，从调试器中） 时，您可以键入**处理**框。  
  
     - 或 -  
  
     如果您知道的标题和/或所需的窗口类，您可以键入它们**标题**并**类**文本框中，然后清除**处理**文本框。  
  
4.  选择**向上**或**向下**搜索的初始方向。  
  
5.  单击 **“确定”**。  
  
     如果找到匹配的窗口，它以突出显示[Windows 视图](../debugger/windows-view.md)窗口。



