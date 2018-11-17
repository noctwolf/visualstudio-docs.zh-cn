---
title: 如何： 在高性能群集上进行调试 |Microsoft Docs
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
- cluster debugging
- high-perfomance debugging
ms.assetid: a2f0eb07-840e-4f95-a1b1-9509217e5b8f
caps.latest.revision: 27
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 75f2a96df18137f04b8b7637940c70378842e23d
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51747725"
---
# <a name="how-to-debug-on-a-high-performance-cluster"></a>如何：在高性能群集上进行调试
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

在高性能群集上调试多处理程序类似于在远程计算机上调试普通程序。 但是，还有一些其他注意事项。 有关常规远程设置要求，请参阅[远程调试](../debugger/remote-debugging.md)。  
  
 当在高性能群集上进行调试时，可以使用所有可用于远程调试的 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 调试窗口和技术。 但是由于你正在进行远程调试，所以外部控制台窗口不可用。  
  
 **线程**窗口和**进程**窗口是对于调试并行应用程序特别有用。 有关如何使用这些窗口的提示，请参阅[如何： 使用进程窗口](http://msdn.microsoft.com/en-us/0207ce2f-8ceb-4fe7-b2b5-4dd35b035ed7)并[如何： 使用线程窗口](../debugger/how-to-use-the-threads-window.md)。  
  
 下面的过程演示在高性能群集上调试时特别有用的一些技术。  
  
 调试并行应用程序时，你可能希望在特定的线程、进程或计算机上设置断点。 可以通过创建普通断点，然后添加断点筛选器来做到这一点。  
  
### <a name="to-open-the-breakpoint-filter-dialog-box"></a>打开“断点筛选器”对话框  
  
1.  右键单击断点标志符号在源窗口中，**反汇编**窗口中，**调用堆栈**窗口中，或**断点**窗口。  
  
2.  在快捷菜单上，单击**筛选器**。 此选项可能级别或在子菜单下显示在顶部**断点**。  
  
### <a name="to-set-a-breakpoint-on-a-specific-computer"></a>在特定计算机中设置断点  
  
1.  获取计算机名称从**进程**窗口。  
  
2.  选择一个断点，并打开**断点筛选器**对话框中，如前面的过程中所述。  
  
3.  在中**断点筛选器**对话框中，键入：  
  
     MachineName =*你的计算机名称*  
  
     若要创建更复杂的筛选器，可以使用 `&`（“与”运算符）、`||`（“或”运算符）、`!`（“非”运算符）和括号组合子句。  
  
4.  单击 **“确定”**。  
  
### <a name="to-set-a-breakpoint-on-a-specific-process"></a>在特定进程上设置断点  
  
1.  获取进程名称或进程 ID 号，从**进程**窗口。  
  
2.  选择一个断点，并打开**断点筛选器**如第一个过程中所示的对话框。  
  
3.  在中**断点筛选器**对话框中，键入：  
  
     `ProcessName =`  *yourprocessname*  
  
     - 或 -  
  
     `ProcessID =` *yourprocessIDnumber*  
  
     若要创建更复杂的筛选器，可以使用 `&`（“与”运算符）、`||`（“或”运算符）、`!`（“非”运算符）和括号组合子句。  
  
4.  单击 **“确定”**。  
  
### <a name="to-set-a-breakpoint-on-a-specific-thread"></a>在特定线程上设置断点  
  
1.  获取线程名称或线程 ID 号，从**线程**窗口。  
  
2.  选择一个断点，并打开**断点筛选器**对话框中的第一个过程中所述。  
  
3.  在中**断点筛选器**对话框中，键入：  
  
     `ThreadName =` *yourthreadname*  
  
     - 或 -  
  
     `ThreadID =` *yourthreadIDnumber*  
  
     若要创建更复杂的筛选器，可以使用 `&`（“与”运算符）、`||`（“或”运算符）、`!`（“非”运算符）和括号组合子句。  
  
4.  单击 **“确定”**。  
  
## <a name="example"></a>示例  
 下面的示例演示如何在名为 `marvin` 的计算机上的、名为 `fourier1` 的线程上创建一个断点筛选器。  
  
```  
(MachineName = marvin) & (ThreadName = fourier1)  
```  
  
## <a name="see-also"></a>请参阅  
 [调试多线程应用程序](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [远程调试](../debugger/remote-debugging.md)   
 [如何： 使用进程窗口](http://msdn.microsoft.com/en-us/0207ce2f-8ceb-4fe7-b2b5-4dd35b035ed7)   
 [如何： 使用线程窗口](../debugger/how-to-use-the-threads-window.md)   
 [线程和进程](http://msdn.microsoft.com/en-us/73d87480-9af3-4d1b-baf5-397d5d876ae6)   
 [使用断点](../debugger/using-breakpoints.md)



