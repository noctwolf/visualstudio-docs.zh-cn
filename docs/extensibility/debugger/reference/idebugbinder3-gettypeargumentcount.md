---
title: IDebugBinder3::GetTypeArgumentCount |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBinder3::GetTypeArgumentCount
helpviewer_keywords:
- IDebugBinder3::GetTypeArgumentCount method
ms.assetid: caf68de6-6f7c-4efd-b803-121347a5032e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3ffe64b5977ce57130d2c97720442a4b030c1ac4
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53986175"
---
# <a name="idebugbinder3gettypeargumentcount"></a>IDebugBinder3::GetTypeArgumentCount
此方法返回与此对象关联的自变量类型的数字。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetTypeArgumentCount(  
   UINT* uCount  
);  
```  
  
```csharp  
int GetTypeArgumentCount(  
   out uint uCount  
);  
```  
  
#### <a name="parameters"></a>参数  
 `uCount`  
 [out]与此对象关联的参数类型的数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法返回的值可用于以用于分配数组[GetTypeArguments](../../../extensibility/debugger/reference/idebugbinder3-gettypearguments.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)   
 [GetTypeArguments](../../../extensibility/debugger/reference/idebugbinder3-gettypearguments.md)