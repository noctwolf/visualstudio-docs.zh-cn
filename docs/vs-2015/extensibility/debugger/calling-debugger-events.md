---
title: 调用调试器事件 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: b3440ac3-80af-40c6-bef4-cbf00fa67885
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 86c48d072baa53cf3f8ba0a6d903021e6c396afa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47477549"
---
# <a name="calling-debugger-events"></a>调用调试器事件
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[调用调试器事件](https://docs.microsoft.com/visualstudio/extensibility/debugger/calling-debugger-events)。  
  
调试会话中的事件将按特定顺序发生。  
  
## <a name="discussion"></a>讨论  
 若要了解的调试引擎 (DE) 和会话调试管理器 (SDM) 之间的调用模式，以下内容代表典型的调试会话中发生的事件的调用顺序：  
  
1.  [附加和分离到程序](../../extensibility/debugger/attaching-and-detaching-to-a-program.md)  
  
2.  [启动调试器](../../extensibility/debugger/launching-the-debugger.md)  
  
3.  [终止程序](../../extensibility/debugger/terminating-a-program.md)  
  
4.  [创建断点](../../extensibility/debugger/creating-a-breakpoint.md)  
  
5.  [当断点绑定或成为取消绑定](../../extensibility/debugger/when-a-breakpoint-binds-or-becomes-unbound.md)  
  
6.  [断点错误](../../extensibility/debugger/breakpoint-errors.md)  
  
7.  [命中断点](../../extensibility/debugger/hitting-a-breakpoint.md)  
  
8.  [删除断点](../../extensibility/debugger/deleting-a-breakpoint.md)  
  
9. [进入中断模式](../../extensibility/debugger/entering-break-mode.md)  
  
10. [在中断模式下单步执行](../../extensibility/debugger/stepping-in-break-mode.md)  
  
11. [在中断模式下的表达式计算](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
12. [异常处理](../../extensibility/debugger/exception-handling-visual-studio-sdk.md)  
  
## <a name="see-also"></a>请参阅  
 [创建自定义调试引擎](../../extensibility/debugger/creating-a-custom-debug-engine.md)

