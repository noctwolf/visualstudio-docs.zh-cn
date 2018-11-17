---
title: 命中断点 |Microsoft Docs
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
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1b2eef9b068a64f62a955cb21feb8ff445ca0fe9
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51720770"
---
# <a name="hitting-a-breakpoint"></a>命中断点
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

下面介绍的调试引擎 (DE) 遇到断点时在运行或单步执行该过程：  
  
## <a name="troubleshooting-a-hit-breakpoint"></a>故障排除命中的断点  
  
1.  DE 发送[IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md)接口用作**EVENT_SYNC_STOP**。  
  
2.  会话调试管理器 (SDM) 调用[IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md)若要获取已被命中的断点。  
  
## <a name="see-also"></a>请参阅  
 [调用调试器事件](../../extensibility/debugger/calling-debugger-events.md)

