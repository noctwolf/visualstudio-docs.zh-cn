---
title: IDebugProcessEx2::Detach |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcessEx2::Detach
helpviewer_keywords:
- IDebugProcessEx2::Detach method
ms.assetid: 66d54c2c-9302-47c8-9975-f30ed988ab29
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0423ae28bfee6e9acf10e2a9682e58a973c37d70
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31114260"
---
# <a name="idebugprocessex2detach"></a>IDebugProcessEx2::Detach
此方法将通知过程会话不再调试进程。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Detach(   
   IDebugSession2* pSession  
);  
```  
  
```csharp  
int Detach(  
   IDebugSession2 pSession  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pSession`  
 [in]一个值，唯一标识要分离从此进程的会话。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 接口中进行传递`pSession`是若要仅作为 cookie 处理，用于唯一标识会话调试管理器，它最初的值附加到此过程; 提供的接口上的方法都正常工作。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugProcessEx2](../../../extensibility/debugger/reference/idebugprocessex2.md)