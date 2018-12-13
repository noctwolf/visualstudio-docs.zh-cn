---
title: 历史调试 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7cc5ddf2-2f7c-4f83-b7ca-58e92e9bfdd2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a622fcb91ad40e7d0777f37ce87e9a2cb950695
ms.sourcegitcommit: a749c287ec7d54148505978e8ca55ccd406b71ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46542398"
---
# <a name="historical-debugging"></a>历史调试
历史调试是取决于 IntelliTrace 所收集的信息的模式模式。 它允许你向前和前后移动应用程序的执行，并检查其状态。  
  
 可以在 Visual Studio Enterprise 版（但不可在 Professional 或 Community 版）中使用 IntelliTrace。  
  
## <a name="why-use-historical-debugging"></a>为什么要使用历史调试？  
 设置断点以查找 Bug 会是一件没有太多确定性的事情。 在紧邻代码中你怀疑可能存在 Bug 的位置设置断点，然后在调试中程序中运行应用程序，并希望命中断点且执行中断的位置可以揭示 Bug 的源。 否则，将需要尝试设置一个断点在代码中的其他位置，然后重新运行调试器，反复执行测试步骤，直到找到问题。  
  
 ![设置断点](../debugger/media/breakpointprocesa.png "BreakpointProcesa")  
  
 可以使用 IntelliTrace 和历史调试你的应用程序中四处漫游，以查看其状态 （调用堆栈和局部变量），而无需设置断点，请重新启动调试，并重复测试步骤。 这可以为你节省大量时间，特别是在 Bug 位于需要很长时间才能完成执行的测试方案的深处时。  
  
## <a name="how-do-i-start-using-historical-debugging"></a>如何开始使用历史调试？  
 默认启用 IntelliTrace。 您需要做的只是决定哪些事件和函数调用感兴趣，并且是否想要查看完整的应用程序状态的快照。 有关定义你想要查找的详细信息，请参阅[IntelliTrace 功能](../debugger/intellitrace-features.md)。  

 - 若要查看使用历史调试快照，请参阅[检查使用 IntelliTrace 的上一个应用程序状态](../debugger/view-historical-application-state.md)
 - 若要了解如何检查变量和导航代码，请参阅[检查使用历史调试对应用程序](../debugger/historical-debugging-inspect-app.md)
 - 若要了解有关使用 IntelliTrace 事件进行调试的详细信息，请参阅[演练： 使用 IntelliTrace](../debugger/walkthrough-using-intellitrace.md)。