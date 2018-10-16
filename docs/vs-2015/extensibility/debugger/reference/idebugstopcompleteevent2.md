---
title: IDebugStopCompleteEvent2 |Microsoft Docs
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
- IDebugStopCompleteEvent2 interface
ms.assetid: ff3e89f4-61bb-489d-901c-447260100218
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e30b59968fb8eca14d462ce34d12378132771b68
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49195203"
---
# <a name="idebugstopcompleteevent2"></a>IDebugStopCompleteEvent2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

程序已停止时，调试引擎 (DE) 可以向会话调试管理器 (SDM) 发送此可选事件。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugStopCompleteEvent2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者的说明  
 这是适合的新界面[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]。 以前的版本不支持异步停止。  
  
 [停止](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)SDM 在多进程或多程序的情况下调用。 当一个程序将停止事件发送到 SDM 时，SDM 请求停止，过其他程序。  
  
 它用来以异步方式通知程序已经停止 SDM。 这可用于解释器调试引擎，其中有时不运行任何代码在调试的程序，因此[停止](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)未以同步方式完成。 如果调试引擎想要使用此异步通知时，它必须返回`S_ASYNC_STOP`从[停止](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)。  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll

