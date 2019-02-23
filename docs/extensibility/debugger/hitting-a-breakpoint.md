---
title: 命中断点 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 29e0fb7a5fe9cfa107bdbc4ced90cbea2967b77a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56707310"
---
# <a name="hit-a-breakpoint"></a>命中断点
调试引擎 (DE) 运行或单步执行时达到断点时，以下部分描述的过程：

## <a name="troubleshoot-a-hit-breakpoint"></a>排查命中的断点

1.  DE 发送[IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md)接口用作**EVENT_SYNC_STOP**。

2.  会话调试管理器 (SDM) 调用[IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md)若要获取已被命中的断点。

## <a name="see-also"></a>请参阅
- [调用调试器事件](../../extensibility/debugger/calling-debugger-events.md)