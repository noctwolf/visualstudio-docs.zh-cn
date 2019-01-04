---
title: IDebugCoreServer2::GetPort |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer2::GetPort
helpviewer_keywords:
- IDebugCoreServer2::GetPort
ms.assetid: 3f5ea4a8-6085-4600-980a-9e48f8b5be56
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6d9f2ba3699337191a9aa11b8b47d9e5f6101bf2
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53965390"
---
# <a name="idebugcoreserver2getport"></a>IDebugCoreServer2::GetPort
检索特定端口。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetPort(   
   REFGUID       guidPort,  
   IDebugPort2** ppPort  
);  
```  
  
```csharp  
int GetPort(   
   ref Guid        guidPort,  
   out IDebugPort2 ppPort  
);  
```  
  
#### <a name="parameters"></a>参数  
 `guidPort`  
 [in]要检索的端口的 GUID。  
  
 `ppPort`  
 [out]返回[IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)对象，表示所需的端口。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。 返回`E_PORTSUPPLIER_NO_PORT`是否存在具有给定标识符的任何端口。  
  
## <a name="see-also"></a>请参阅  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)