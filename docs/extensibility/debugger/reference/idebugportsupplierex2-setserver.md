---
title: IDebugPortSupplierEx2::SetServer | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugPortSupplierEx2::SetServer
ms.assetid: 0e8ef194-3a4f-4abf-8382-4607ab3005d1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: defc13ea9bc63bc1e2c5bdca229e58ec71fe25dc
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54950009"
---
# <a name="idebugportsupplierex2setserver"></a>IDebugPortSupplierEx2::SetServer
设置端口提供程序的核心服务器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetServer(  
   IDebugCoreServer2* pServer  
);  
```  
  
```csharp  
int SetServer(  
   IDebugCoreServer2 pServer  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pServer`  
 若要设置的端口提供程序的核心服务器。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPortSupplierEx2](../../../extensibility/debugger/reference/idebugportsupplierex2.md)