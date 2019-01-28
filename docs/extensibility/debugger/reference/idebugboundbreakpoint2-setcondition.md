---
title: IDebugBoundBreakpoint2::SetCondition | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBoundBreakpoint2::SetCondition
helpviewer_keywords:
- SetCondition method
- IDebugBoundBreakpoint2::SetCondition method
ms.assetid: 5d366876-efed-43d0-8ea1-dfdb009cbfac
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: dac748f78428b49e17fe350e74147b62ebd64ea6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55023897"
---
# <a name="idebugboundbreakpoint2setcondition"></a>IDebugBoundBreakpoint2::SetCondition
设置或更改与此绑定断点相关联的条件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetCondition(   
   BP_CONDITION bpCondition  
);  
```  
  
```csharp  
int SetCondition(   
   enum_BP_CONDITION bpCondition  
);  
```  
  
#### <a name="parameters"></a>参数  
 `bpCondition`  
 [in]中的值[BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)枚举，用于描述该条件。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。 返回`E_BP_DELETED`如果绑定的断点对象的状态设置为`BPS_DELETED`(属于[BP_STATE](../../../extensibility/debugger/reference/bp-state.md)枚举)。  
  
## <a name="remarks"></a>备注  
 以前有与此断点关联的任何条件会丢失。  
  
## <a name="see-also"></a>请参阅  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)   
 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)