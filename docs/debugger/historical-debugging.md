---
title: 历史调试 |Microsoft 文档
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
ms.openlocfilehash: a75dfc04bd5ce3b1e61cc2c8e8fe293c13560cf9
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31479671"
---
# <a name="historical-debugging"></a>历史调试
历史调试是取决于 IntelliTrace 所收集的信息的模式模式。 它允许你向前和前后移动应用程序的执行，并检查其状态。  
  
 可以在 Visual Studio Enterprise 版（但不可在 Professional 或 Community 版）中使用 IntelliTrace。  
  
## <a name="why-use-historical-debugging"></a>为何使用历史调试？  
 设置断点以查找 Bug 会是一件没有太多确定性的事情。 在紧邻代码中你怀疑可能存在 Bug 的位置设置断点，然后在调试中程序中运行应用程序，并希望命中断点且执行中断的位置可以揭示 Bug 的源。 如果没有，则需要尝试在代码中的其他某处设置断点并重新运行调试程序时，反复执行测试步骤直到发现问题。  
  
 ![设置断点](../debugger/media/breakpointprocesa.png "BreakpointProcesa")  
  
 你可以使用 IntelliTrace 和历史调试在你的应用程序中四处漫游，并检查其状态 （调用堆栈和局部变量） 而无需设置断点，请重新启动调试，且不重复测试步骤。 这可以为你节省大量时间，特别是在 Bug 位于需要很长时间才能完成执行的测试方案的深处时。  
  
## <a name="how-do-i-start-using-historical-debugging"></a>如何开始使用历史调试？  
 默认启用 IntelliTrace。 你所要做的就是确定哪些事件和函数调用是感兴趣，以及是否想要查看完整的应用程序状态的快照。 有关定义你想要查找的详细信息，请参阅[IntelliTrace 功能](../debugger/intellitrace-features.md)。  

 - 若要查看使用历史调试的快照，请参阅[查看使用 IntelliTrace 步骤后的快照](../debugger/how-to-use-intellitrace-step-back.md)
 - 若要了解如何检查变量和浏览代码，请参阅[检查你的应用使用历史调试](../debugger/historical-debugging-inspect-app.md)
 - 若要了解有关使用 IntelliTrace 事件进行调试的详细信息，请参阅[演练： 使用 IntelliTrace](../debugger/walkthrough-using-intellitrace.md)。