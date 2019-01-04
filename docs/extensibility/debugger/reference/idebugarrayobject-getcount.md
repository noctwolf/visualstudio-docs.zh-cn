---
title: IDebugArrayObject::GetCount |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugArrayObject::GetCount
helpviewer_keywords:
- IDebugArrayObject::GetCount method
ms.assetid: 7931f3f7-033c-4bf8-8abd-95183952ebb0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1ab25e2dacce444ad8b72bb86dc2e07bf7ae8c34
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53908600"
---
# <a name="idebugarrayobjectgetcount"></a>IDebugArrayObject::GetCount
获取数组中元素的计数。  
  
## <a name="syntax"></a>语法  
  
```  
[C++]  
HRESULT GetCount(   
   DWORD* pdwElements  
);  
```  
  
```  
[C#]  
int GetCount(  
   out uint pdwElements  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdwElements`  
 [out]返回的计数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法将所有数组对象的元素视为一维数组，即使是多维的数组对象。 例如，给定数组`myarray[3][2][6]`，此方法将返回在 36`pdwElements`参数。 使用[GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md)方法一次检索一个单独的元素。  
  
## <a name="see-also"></a>请参阅  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)