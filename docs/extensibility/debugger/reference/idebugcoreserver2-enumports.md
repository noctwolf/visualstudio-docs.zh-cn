---
title: IDebugCoreServer2::EnumPorts | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer2::EnumPorts
helpviewer_keywords:
- IDebugCoreServer2::EnumPorts
ms.assetid: 3d98dfd0-614f-4d68-90c6-8a9b9cab66f1
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0555c9167ae24ad1ea700af142d4598117c58f3a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55037975"
---
# <a name="idebugcoreserver2enumports"></a>IDebugCoreServer2::EnumPorts
检索所有可用的端口的列表。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumPorts(   
   IEnumDebugPorts2** ppEnum  
);  
```  
  
```csharp  
int EnumPorts(   
   out IEnumDebugPorts2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppEnum`  
 [out]返回[IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)对象，其中包含从所有端口供应商的所有端口的列表。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)