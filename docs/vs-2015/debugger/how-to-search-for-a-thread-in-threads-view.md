---
title: 如何： 搜索线程视图中的线程 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- threads, searching
ms.assetid: 5609a9b3-c279-4426-9e2e-dd87896a6d6f
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ed11edadca2f5e5e521eda824ece5ab735814125
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49912164"
---
# <a name="how-to-search-for-a-thread-in-threads-view"></a>如何：在线程视图中搜索线程
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

可以通过将其线程 ID 或模块字符串用作搜索条件来搜索特定线程在线程视图中。 此外可以指定搜索的初始传递方向。 在对话框中的字段将线程树中显示所选线程的属性。  
  
### <a name="to-search-for-a-thread-in-threads-view"></a>若要搜索的线程视图中的线程  
  
1. 排列窗口，因此该 Spy + + 和活动[线程视图](../debugger/threads-view.md)是可见的窗口。  
  
2. 从**搜索**菜单中，选择**查找线程**。  
  
    [线程搜索对话框](../debugger/thread-search-dialog-box.md)随即打开。  
  
3. 键入的线程 ID 或模块字符串作为搜索条件。  
  
4. 清除不想为其指定值的任何字段。  
  
   > [!TIP]
   >  若要查找模块拥有的所有线程，请清除**线程**中的文本框然后键入该模块名称**模块**框。 然后，使用**查找下一个**表示不继续搜索的线程。  
  
5. 选择**向上**或**向下**搜索的初始方向。  
  
6. 单击 **“确定”**。  
  
   如果找到匹配的线程，则它将突出显示在线程视图窗口中。



