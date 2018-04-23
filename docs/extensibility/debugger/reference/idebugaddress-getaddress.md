---
title: IDebugAddress::GetAddress |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugAddress::GetAddress
helpviewer_keywords:
- IDebugAddress:GetAddress method
ms.assetid: 2590387b-5d36-4116-9a75-737957b8898e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e7f93b57d3cdbea71d3cf9cbe3d51645251c9628
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idebugaddressgetaddress"></a>IDebugAddress::GetAddress
返回描述对象并将其位置在其作用域或容器的结构。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetAddress (  
   DEBUG_ADDRESS * pAddress  
);  
```  
  
```csharp  
int GetAddress(  
   DEBUG_ADDRESS[] pAddress  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pAddress`  
 [在中，out]A [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)此方法由填充的结构。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)结构传递给此方法，然后使用相应信息对其进行填充。 如何解释此信息取决于返回的信息和符号处理程序本身的类型。 请参阅[DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)有关详细信息。  
  
## <a name="see-also"></a>另请参阅  
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)