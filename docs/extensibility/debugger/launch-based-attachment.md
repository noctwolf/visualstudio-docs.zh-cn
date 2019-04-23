---
title: 基于启动的附件 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, launching
- debug engines, attaching to programs
ms.assetid: 362f00ac-1909-4a3a-bacb-c0ceb5549816
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0cf41afa91ce1e77904b99f17ea0321e9bdb12d1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "60091715"
---
# <a name="launch-based-attachment"></a>基于启动的附件
基于启动的附件添加到某个程序是自动的。 托管程序的进程启动时通过 SDM，基于启动的附件遵循一个类似于手动附件方法的路径。 有关信息，请参阅[附加到程序](../../extensibility/debugger/attaching-to-the-program.md)。

## <a name="the-attaching-process"></a>附加进程
 主要区别是事件的顺序**附加**调用，请按如下所示：

1. 发送**IDebugEngineCreateEvent2**到 SDM 事件对象。 有关详细信息，请参阅[将事件发送](../../extensibility/debugger/sending-events.md)。

2. 调用`IDebugProgram2::GetProgramId`方法**IDebugProgram2**接口传递给**附加**方法。

3. 发送**IDebugProgramCreateEvent2**事件对象，以通知 SDM 的本地**IDebugProgram2**创建对象时用于表示 DE 程序。

4. 发送[IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md)事件对象，以通知 SDM 启动的进程会创建一个新线程。

## <a name="see-also"></a>请参阅
- [发送所需的事件](../../extensibility/debugger/sending-the-required-events.md)
- [启用要进行调试的程序](../../extensibility/debugger/enabling-a-program-to-be-debugged.md)