---
title: IDebugThread2::Suspend |Microsoft Docs
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
- IDebugThread2::Suspend
helpviewer_keywords:
- IDebugThread2::Suspend
ms.assetid: 1e20be85-aa12-48de-bb83-0bf0976e99ae
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 164d3b79c7c76ad2075fbae04e198a381c808bd8
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51802767"
---
# <a name="idebugthread2suspend"></a>IDebugThread2::Suspend
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

将线程挂起。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Suspend (   
   DWORD *pdwSuspendCount  
);  
```  
  
```csharp  
HRESULT Suspend (   
   out uint pdwSuspendCount  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdwSuspendCount`  
 [out]挂起操作完成后返回的挂起计数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 每次调用此方法递增的挂起计数大于 0。 此挂起计数显示在**线程**调试窗口。  
  
 对于每次调用此方法，必须稍后调用[Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [Resume](../../../extensibility/debugger/reference/idebugthread2-resume.md)

