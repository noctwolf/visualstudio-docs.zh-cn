---
title: IDebugModule3::SetJustMyCodeState | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugModule3::SetJustMyCodeState
helpviewer_keywords:
- IDebugModule3::SetJustMyCodeState
ms.assetid: 68f8166d-ef64-49ae-ad5e-79604f43bbd4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: faa3348f7916e7d56cbdd4c279a09dcc2b5ccdab
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55008174"
---
# <a name="idebugmodule3setjustmycodestate"></a>IDebugModule3::SetJustMyCodeState
将标记作为或不被用户代码的模块。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetJustMyCodeState(  
   BOOL fIsUserCode  
);  
```  
  
```csharp  
int SetJustMyCodeState(  
   int fIsUserCode  
);  
```  
  
#### <a name="parameters"></a>参数  
 `fIsUserCode`  
 [in]非零值 (`TRUE`) 如果模块应被视为用户代码，零 (`FALSE`) 如果不应。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为将返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugModule3](../../../extensibility/debugger/reference/idebugmodule3.md)