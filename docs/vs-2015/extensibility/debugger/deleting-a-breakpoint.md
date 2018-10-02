---
title: 删除断点 |Microsoft Docs
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
- breakpoints, deleting
- debugging [Debugging SDK], deleting breakpoints
ms.assetid: 75a046cc-d20a-4c79-ad2d-1f18426ac5d0
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 18b88cc55a4c641e56c062356a9f74c2224835a8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479904"
---
# <a name="deleting-a-breakpoint"></a>删除断点
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[删除断点](https://docs.microsoft.com/visualstudio/extensibility/debugger/deleting-a-breakpoint)。  
  
下面介绍删除挂起断点时的过程：  
  
## <a name="deletion-process"></a>删除过程  
 会话调试管理器 (SDM) 调用[IDebugPendingBreakpoint2::Delete](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md)方法移除挂起断点和所有绑定的断点绑定从它。  
  
> [!NOTE]
>  此外可以通过调用删除单个绑定的断点[IDebugBoundBreakpoint2::Delete](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)。  
  
## <a name="see-also"></a>请参阅  
 [调用调试器事件](../../extensibility/debugger/calling-debugger-events.md)

