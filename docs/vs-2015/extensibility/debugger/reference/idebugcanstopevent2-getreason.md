---
title: IDebugCanStopEvent2::GetReason |Microsoft Docs
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
- IDebugCanStopEvent2::GetReason
helpviewer_keywords:
- IDebugCanStopEvent2::GetReason
ms.assetid: f5de31ca-7b8d-4029-9cf9-ba860ac66af6
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5d34802ccf4abe16d4fc6b7428405dd89558b5f6
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51795279"
---
# <a name="idebugcanstopevent2getreason"></a>IDebugCanStopEvent2::GetReason
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

获取调试引擎 (DE) 是为什么想要停止的原因。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetReason(   
   CANSTOP_REASON* pcr  
);  
```  
  
```csharp  
int GetReason(   
   out enum_CANSTOP_REASON pcr  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pcr`  
 [out]返回一个值从[CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md)介绍了此事件的原因的枚举。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法通常称为之前[CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)方法，以便调用方可以确定是否将传递非零值 (`TRUE`) 到`IDebugCanStopEvent2::CanStop`方法。  
  
 正在停止的原因可以是`CANSTOP_ENTRYPOINT`，这意味着 DE 已达到的入口点，或`CANSTOP_STEPIN`，这意味着 DE 单步执行函数。  
  
## <a name="see-also"></a>请参阅  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [CANSTOP_REASON](../../../extensibility/debugger/reference/canstop-reason.md)   
 [CanStop](../../../extensibility/debugger/reference/idebugcanstopevent2-canstop.md)

