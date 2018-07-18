---
title: IDebugThread2::GetThreadId |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugThread2::GetThreadId
helpviewer_keywords:
- IDebugThread2::GetThreadId
ms.assetid: db8b1c07-6b86-47f9-b292-bac19c276d36
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ac1701b3f52975e962860d558bc70b1847eef8e5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31122374"
---
# <a name="idebugthread2getthreadid"></a>IDebugThread2::GetThreadId
获取系统线程标识符。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetThreadId (   
   DWORD* pdwThreadId  
);  
```  
  
```csharp  
int GetThreadId (   
   out uint pdwThreadId  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdwThreadId`  
 [out]返回系统线程标识符。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 线程 ID 用于标识进程中的其他所有线程间的线程。  
  
## <a name="example"></a>示例  
 下面的示例演示如何实现此方法对于简单`CProgram`实现对象[IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)接口。  
  
```cpp  
HRESULT CProgram::GetThreadId(DWORD* pdwThreadId) {     
   *pdwThreadId = GetCurrentThreadId();    
   return NOERROR;    
}    
```  
  
## <a name="see-also"></a>另请参阅  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)