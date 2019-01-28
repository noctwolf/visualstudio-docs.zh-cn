---
title: IDebugProcess2::EnumThreads | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProcess2::EnumThreads
helpviewer_keywords:
- IDebugProcess2::EnumThreads
ms.assetid: 05677385-7a7f-4545-8438-af00dde85db0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5353d10887991008a4fb7ab39262cdfeb77bafae
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54953729"
---
# <a name="idebugprocess2enumthreads"></a>IDebugProcess2::EnumThreads
检索在进程中运行的所有线程的列表。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumThreads(  
   IEnumDebugThreads2** ppEnum  
);  
```  
  
```csharp  
int EnumThreads(  
   out IEnumDebugThreads2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppEnum`  
 [out]返回[IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)对象，其中包含一系列过程中的所有程序中的所有线程。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法枚举每个程序中正在运行的线程，然后将它们合并到线程的进程视图。 单个线程可能会运行多个程序;此方法一次枚举该线程。  
  
 此方法会显示该进程的线程没有重复项的列表。 否则，若要枚举在特定的程序中运行的线程，请使用[EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IEnumDebugThreads2](../../../extensibility/debugger/reference/ienumdebugthreads2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)