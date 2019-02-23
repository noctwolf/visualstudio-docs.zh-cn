---
title: 终止和分离 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- programs, termination events
- debug engines, detaching from programs
ms.assetid: 268c1e51-6363-45d1-964c-1ab99bdfa4f9
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a727f30f6070b44e16dbc4206ac56e0224ff3d67
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56682162"
---
# <a name="termination-and-detaching"></a>终止和分离
以下部分介绍正常终止。

## <a name="discussion"></a>讨论
 之后[IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md)或[IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md)接口仍然存在，如果没有任何断点、 异常、 运行时错误或要进行调试的应用程序中的无限循环正在调试的程序运行完成。 此过程是正常终止。

 必须在发送[IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)实现正常终止。 正常终止需要运行[IDebugProgramDestroyEvent2::GetExitCode](../../extensibility/debugger/reference/idebugprogramdestroyevent2-getexitcode.md)方法。

## <a name="see-also"></a>请参阅
- [创建自定义调试引擎](../../extensibility/debugger/creating-a-custom-debug-engine.md)