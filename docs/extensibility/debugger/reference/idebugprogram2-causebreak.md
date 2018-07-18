---
title: IDebugProgram2::CauseBreak |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::CauseBreak
helpviewer_keywords:
- IDebugProgram2::CauseBreak
ms.assetid: 07d353fc-68ab-4297-a18f-3d3c7a80e121
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 81fb04db3342bb8ce7d5e314c9a912b873ffb627
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31116394"
---
# <a name="idebugprogram2causebreak"></a>IDebugProgram2::CauseBreak
程序停止执行下一步的请求的时间其线程尝试运行之一。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CauseBreak(   
   void   
);  
```  
  
```csharp  
int CauseBreak();  
```  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)程序接下来尝试调用此方法之后，运行代码时不会发送事件。  
  
 此方法是异步的因为该方法将立即返回而不一定等待程序停止。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)