---
title: IDebugExceptionEvent2::PassToDebuggee |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugExceptionEvent2::PassToDebuggee
helpviewer_keywords:
- IDebugExceptionEvent2::PassToDebuggee
ms.assetid: a20d0f0b-2ca0-4437-bd22-9213c81d2738
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 937afe676ffecbada7a21480ceeb5c16d607006d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49252442"
---
# <a name="idebugexceptionevent2passtodebuggee"></a>IDebugExceptionEvent2::PassToDebuggee
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

指定异常应传递到时恢复执行，正在调试的程序还是应放弃该异常。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT PassToDebuggee(  
   BOOL fPass  
);  
```  
  
```csharp  
int PassToDebuggee(  
   int fPass  
);  
```  
  
#### <a name="parameters"></a>参数  
 `fPass`  
 [in]非零值 (`TRUE`) 如果异常应传递到时恢复执行，正在调试的程序或零 (`FALSE`) 如果应放弃该异常。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 调用此方法不会实际导致要在正在调试的程序中执行的任何代码。 在调用是只是设置下一步执行代码的状态。 例如，调用[CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)方法可能会返回`S_OK`与[EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)。`dwState` 字段设置为`EXCEPTION_STOP_SECOND_CHANCE`。  
  
 IDE 可能会收到[IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)事件，并调用[继续](../../../extensibility/debugger/reference/idebugprogram2-continue.md)方法。 调试引擎 (DE) 应具有一个默认行为来处理如果`PassToDebuggee`不会调用方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [CanPassToDebuggee](../../../extensibility/debugger/reference/idebugexceptionevent2-canpasstodebuggee.md)   
 [Continue](../../../extensibility/debugger/reference/idebugprogram2-continue.md)

