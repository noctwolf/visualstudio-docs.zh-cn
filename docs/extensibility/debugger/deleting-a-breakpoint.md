---
title: 删除断点 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- breakpoints, deleting
- debugging [Debugging SDK], deleting breakpoints
ms.assetid: 75a046cc-d20a-4c79-ad2d-1f18426ac5d0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a8f2a4047fb44e2967e281becd90c78f66de9fdb
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63410015"
---
# <a name="deleting-a-breakpoint"></a>删除断点
下面介绍删除挂起断点时的过程：

## <a name="deletion-process"></a>删除过程
 会话调试管理器 (SDM) 调用[IDebugPendingBreakpoint2::Delete](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md)方法移除挂起断点和所有绑定的断点绑定从它。

> [!NOTE]
> 此外可以通过调用删除单个绑定的断点[IDebugBoundBreakpoint2::Delete](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md)。

## <a name="see-also"></a>请参阅
- [调用调试器事件](../../extensibility/debugger/calling-debugger-events.md)