---
title: IDebugBinder3::GetTypeArguments | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBinder3::GetTypeArguments
helpviewer_keywords:
- IDebugBinder3::GetTypeArguments method
ms.assetid: fa0c37a7-327f-463e-9a9d-bb3f534584cb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a65c27e3ac175c0140b2484f9581642551b8b1ac
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55007693"
---
# <a name="idebugbinder3gettypearguments"></a>IDebugBinder3::GetTypeArguments
此方法检索与此对象关联的参数类型的列表。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetTypeArguments(  
   UINT          skip,  
   UINT          count,  
   IDebugField** ppFields,  
   UINT*         pFetched  
);  
```  
  
```csharp  
int GetTypeArguments(  
   uint          skip,  
   uint          count,  
   IDebugField[] ppFields,  
   out uint      pFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 `skip`  
 [in]若要获取参数类型之前跳过的字段数。  
  
 `count`  
 [in]要返回的参数字段数 (还指定的大小`ppFields`数组)。  
  
 `ppFields`  
 [in、 out]会在此方法返回填充的字段的数组。  
  
 `pFetched`  
 [out]\(可选)实际返回的字段类型的参数的数量。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 自变量类型的数即可获得事先[GetTypeArgumentCount](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md)。  
  
## <a name="see-also"></a>请参阅  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)   
 [GetTypeArgumentCount](../../../extensibility/debugger/reference/idebugbinder3-gettypeargumentcount.md)