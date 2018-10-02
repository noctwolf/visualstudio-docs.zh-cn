---
title: 附加和分离到一个程序 |Microsoft Docs
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
- debug engines, attaching to programs
- debug engines, detaching from programs
ms.assetid: 79dcbb9b-c7f8-40fc-8a00-f37fe1934f51
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a7129fab85d405d941394c02abf79ba29e787f5b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470959"
---
# <a name="attaching-and-detaching-to-a-program"></a>附加到程序和从程序分离
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[附加和分离到一个程序](https://docs.microsoft.com/visualstudio/extensibility/debugger/attaching-and-detaching-to-a-program)。  
  
附加调试器需要发送正确的方法和使用适当的属性的事件顺序。  
  
## <a name="sequence-of-methods-and-events"></a>序列的方法和事件  
  
1.  会话调试管理器 (SDM) 调用[OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)方法。  
  
     基于调试引擎 (DE) 进程模型，`IDebugProgramNodeAttach2::OnAttach`方法返回确定接下来会发生的以下方法之一。  
  
     如果`S_FALSE`返回，调试引擎已成功附加到该程序。 否则为[附加](../../extensibility/debugger/reference/idebugengine2-attach.md)方法调用以完成附加过程。  
  
     如果`S_OK`返回，DE 会加载 SDM 作为在同一进程中。 SDM 执行以下任务：  
  
    1.  调用[GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)了解 DE 引擎。  
  
    2.  共同创建 DE。  
  
    3.  调用[附加](../../extensibility/debugger/reference/idebugengine2-attach.md)。  
  
2.  DE 发送[IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md)到使用 SDM`EVENT_SYNC`属性。  
  
3.  DE 发送[IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md)到使用 SDM`EVENT_SYNC`属性。  
  
4.  DE 发送[IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md)到使用 SDM`EVENT_SYNC_STOP`属性。  
  
 从程序分离很简单，分为两步过程中，如下所示：  
  
1.  SDM 调用[分离](../../extensibility/debugger/reference/idebugprogram2-detach.md)。  
  
2.  DE 发送[IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)。  
  
## <a name="see-also"></a>请参阅  
 [调用调试器事件](../../extensibility/debugger/calling-debugger-events.md)

