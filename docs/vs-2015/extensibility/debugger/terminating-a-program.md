---
title: 终止程序 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- programs, termination events
- debugging [Debugging SDK], terminating a program
ms.assetid: eedda0a3-5e05-44fe-841d-a2f4866ac72d
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cf972e6bb38d9dcd2995814e885ceb0b071abe29
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49294667"
---
# <a name="terminating-a-program"></a>终止程序
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

下面是一个线程使用单个程序终止的说明。  
  
## <a name="termination-process"></a>终止进程  
  
1.  DE 发送[IDebugThreadDestroyEvent2](../../extensibility/debugger/reference/idebugthreaddestroyevent2.md)使用一个有效[IDebugThread2](../../extensibility/debugger/reference/idebugthread2.md)。  
  
2.  DE 发送[IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)使用一个有效[IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)。  
  
 IDE 将进入设计模式。 调试引擎或运行时环境调用[IDebugPortNotify2::RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)从端口删除该程序。  
  
## <a name="see-also"></a>请参阅  
 [调用调试器事件](../../extensibility/debugger/calling-debugger-events.md)

