---
title: IDebugApplicationThread110 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThread110 Interface
ms.assetid: 25bc351f-3451-4387-9302-078f6292ddff
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 170b345bdb4587d1fd29c1f0f906df0157abd877
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348914"
---
# <a name="idebugapplicationthread110-interface"></a>IDebugApplicationThread110 接口
提供的更多功能[IDebugApplicationThread 接口](../../winscript/reference/idebugapplicationthread-interface.md)接口。  
  
> [!IMPORTANT]
>  此接口由 PDM v11.0 和更高版本实现。 在 activdbg100.h 中发现。  
  
## <a name="methods"></a>方法  
 `IDebugApplicationThread110` 接口公开以下方法。  
  
|方法|描述|  
|------------|-----------------|  
|[IDebugApplicationThread110::AsynchronousCallIntoThread](../../winscript/reference/idebugapplicationthread110-asynchronouscallintothread.md)|在主线程上进行异步调用。|  
|[IDebugApplicationThread110::GetActiveThreadRequestCount](../../winscript/reference/idebugapplicationthread110-getactivethreadrequestcount.md)|当前正在处理来自 PDM 的线程切换机制多少线程请求的计数。 0 或 1，但它通常的此属性为更高版本，如果一个线程调用开始进行处理但触发同步调用从线程或否则将线程挂起 （例如，通过触发对调试程序发出的 IDebugApplicationEvents 事件可能线程）|  
|[IDebugApplicationThread110::IsSuspendedForBreakPoint](../../winscript/reference/idebugapplicationthread110-issuspendedforbreakpoint.md)|[IDebugApplicationThreadEvents110::OnSuspendForBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onsuspendforbreakpoint.md)已在此线程上调用，但尚未完成。|  
|[IDebugApplicationThread110::IsThreadCallable](../../winscript/reference/idebugapplicationthread110-isthreadcallable.md)|此线程处于状态，可以处理使用 PDM 的线程切换机制 （例如 SynchronousCallInThread) 所做的调用。|