---
title: 命中断点 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8a9b110abdaf0ebfaed720dd5d09c0e215a6b2e7
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "39231550"
---
# <a name="hit-a-breakpoint"></a>命中断点
调试引擎 (DE) 运行或单步执行时达到断点时，以下部分描述的过程：  
  
## <a name="troubleshoot-a-hit-breakpoint"></a>排查命中的断点  
  
1.  DE 发送[IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md)接口用作**EVENT_SYNC_STOP**。  
  
2.  会话调试管理器 (SDM) 调用[IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md)若要获取已被命中的断点。  
  
## <a name="see-also"></a>请参阅  
 [调用调试器事件](../../extensibility/debugger/calling-debugger-events.md)