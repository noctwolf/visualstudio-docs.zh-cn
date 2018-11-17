---
title: 如何： 在进程视图中的进程搜索 |Microsoft Docs
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
- Processes view
- processes, searching for
ms.assetid: 7cb97b37-4a95-4f1b-9eee-4910aa9c115b
caps.latest.revision: 7
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c187089c8aeec3b2c0409adbab1f262893720d87
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51735607"
---
# <a name="how-to-search-for-a-process-in-processes-view"></a>如何：在进程视图中搜索进程
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

可以通过将其进程 ID 或模块字符串用作搜索条件来搜索特定的进程在进程视图中。 此外可以指定搜索的初始传递方向。 进程树中，在对话框中的字段将显示所选的进程的属性。  
  
### <a name="to-search-for-a-process-in-processes-view"></a>若要在进程视图中的进程搜索  
  
1. 排列窗口，因此该 Spy + + 和活动[进程视图](../debugger/processes-view.md)是可见的窗口。  
  
2. 从**搜索**菜单中，选择**查找进程**  
  
    [进程搜索对话框](../debugger/process-search-dialog-box.md)随即打开。  
  
3. 键入的进程 ID 或模块字符串作为搜索条件。  
  
4. 清除不想为其指定值的任何字段。  
  
   > [!TIP]
   >  若要查找模块拥有的所有进程，请清除**进程**框中，键入中的模块名称**模块**框。 然后，使用**查找下一个**表示不继续搜索的进程。  
  
5. 选择**向上**或**向下**搜索的初始方向。  
  
6. 单击 **“确定”**。  
  
   如果找到匹配的进程，则它以突出显示**进程视图**窗口。



