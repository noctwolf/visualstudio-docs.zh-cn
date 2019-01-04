---
title: IDebugProgram2::CauseBreak |Microsoft Docs
ms.date: 11/04/2016
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
ms.openlocfilehash: c0e30e90aa1778904bc6c6349427c567ea3bb160
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53829665"
---
# <a name="idebugprogram2causebreak"></a>IDebugProgram2::CauseBreak
请求程序停止执行下一步的时间运行其线程尝试之一。  
  
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
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)时接下来，该程序尝试调用此方法之后，运行代码，则会发送事件。  
  
 此方法是异步的方法将立即返回而不一定等待程序停止。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)