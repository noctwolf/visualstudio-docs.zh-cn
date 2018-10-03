---
title: 如何： 调试时切换到另一个线程 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
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
- threads, switching [debugging]
ms.assetid: 5cd76c52-76fa-4fcc-b37e-e9f0ecac0e9e
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c682ddff5fd4dc44fe79fa81c1615362f8121e5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479855"
---
# <a name="how-to-switch-to-another-thread-while-debugging"></a>如何：在调试时切换到另一个线程
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[如何： 切换到另一个线程时调试](https://docs.microsoft.com/visualstudio/debugger/how-to-switch-to-another-thread-while-debugging)。  
  
在调试多线程应用程序时，您可以使用若干方法中的任何一种，将上下文从正在处理的线程切换到另一个线程。  
  
### <a name="to-switch-to-any-thread-that-appears-in-the-threads-window"></a>切换至“线程”窗口中显示的任何线程  
  
-   双击线程。  
  
### <a name="to-switch-to-a-thread-in-a-source-window"></a>切换至源窗口中的线程  
  
-   在左侧的槽中，右击线程指示符，指向**切换到**，然后单击你想要切换的线程的名称。 快捷菜单仅显示该特定位置的线程。  
  
     如果没有指示器显示，请右键单击**线程**窗口，并验证**在源中显示线程**处于选中状态。  
  
### <a name="to-switch-to-a-thread-in-the-debug-location-toolbar"></a>切换到“调试位置”工具栏中的线程  
  
1.  上**调试位置**工具栏上，单击**线程**框。  
  
2.  在列表中，单击要切换到的线程。  
  
## <a name="see-also"></a>请参阅  
 [调试多线程应用程序](../debugger/debug-multithreaded-applications-in-visual-studio.md)



