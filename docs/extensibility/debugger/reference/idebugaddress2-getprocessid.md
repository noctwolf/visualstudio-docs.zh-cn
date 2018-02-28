---
title: "IDebugAddress2::GetProcessID |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugAddress2::GetProcessID
helpviewer_keywords:
- IDebugAddress2::GetProcessID method
ms.assetid: 2c18889d-074a-4b95-87b4-bf1a067f44ed
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: bcc83bf3fd83a0c84fa73e11fc9c25f990bd769b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugaddress2getprocessid"></a>IDebugAddress2::GetProcessID
检索表示该对象所属的进程 ID [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)接口。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetProcessID (  
   DWORD* pProcID  
);  
```  
  
```csharp  
int GetProcessID (  
   out uint pProcID  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pProcID`  
 [out]进程 id。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK;否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)