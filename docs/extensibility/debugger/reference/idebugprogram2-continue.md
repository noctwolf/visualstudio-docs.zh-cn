---
title: IDebugProgram2::Continue |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::Continue
helpviewer_keywords:
- IDebugProgram2::Continue
ms.assetid: e5a6e02a-d21b-4a03-a034-e8de1f71ce2e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f52fccf640cca32d4291b3d6fb8626c38370ded3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31116742"
---
# <a name="idebugprogram2continue"></a>IDebugProgram2::Continue
将继续从停止的状态运行此程序。 保留任何以前的执行状态 （如步骤），并在程序启动再次执行。  
  
> [!NOTE]
>  此方法已弃用。 使用[继续](../../../extensibility/debugger/reference/idebugprocess3-continue.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Continue(   
   IDebugThread2* pThread  
);  
```  
  
```csharp  
int Continue(   
   IDebugThread2 pThread  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pThread`  
 [in][IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)表示的线程的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 在此程序而不考虑正在调试的多少程序，或哪些程序生成 stopping 事件上调用此方法。 实现必须保留以前的执行状态 （如步骤），并继续执行，就像它已完成其之前执行之前永远不会停止。 也就是说，如果此程序中的线程已执行逐过程操作，并且由于某些其他程序停止，然后再调用此方法已停止，程序必须完成原始逐过程操作。  
  
> [!WARNING]
>  不发送 stopping 事件或即时 （同步） 事件与[事件](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)时处理此调用; 否则调试器可能会挂起。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [Event](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)