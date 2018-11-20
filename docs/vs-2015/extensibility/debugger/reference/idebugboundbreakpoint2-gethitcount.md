---
title: IDebugBoundBreakpoint2::GetHitCount |Microsoft Docs
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
- IDebugBoundBreakpoint2::GetHitCount
helpviewer_keywords:
- GetHitCount method
- IDebugBoundBreakpoint2::GetHitCount method
ms.assetid: 23481f37-047c-41d2-8286-4da1f4084961
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c4c9db5e31671881969e927a43cf2c07cddf7edc
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51802052"
---
# <a name="idebugboundbreakpoint2gethitcount"></a>IDebugBoundBreakpoint2::GetHitCount
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

获取此绑定断点的当前命中的计数。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetHitCount(   
   DWORD* pdwHitCount  
);  
```  
  
```csharp  
int GetHitCount(   
   out uint pdwHitCount  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdwHitCount`  
 [out]返回命中的次数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。 返回`E_BP_DELETED`如果绑定的断点对象的状态设置为`BPS_DELETED`(属于[BP_STATE](../../../extensibility/debugger/reference/bp-state.md)枚举)。  
  
## <a name="remarks"></a>备注  
 命中的计数是在会话的当前运行期间已触发此断点的次数。  
  
## <a name="see-also"></a>请参阅  
 [IDebugBoundBreakpoint2](../../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [BP_STATE](../../../extensibility/debugger/reference/bp-state.md)

