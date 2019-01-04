---
title: IDebugBinder3::GetAllAliases |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBinder3::GetAllAliases
helpviewer_keywords:
- IDebugBinder3::GetAllAliases method
ms.assetid: 1f9ab2ee-2ab3-4a61-8b99-95dd7fdf3511
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3733d6582559f8042ec1e7d5d8d8814a0a555c20
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53857278"
---
# <a name="idebugbinder3getallaliases"></a>IDebugBinder3::GetAllAliases
此方法从该程序检索别名的列表。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetAllAliases(  
   UINT          uRequest,  
   IDebugAlias** ppAliases,  
   UINT*         puFetched  
);  
```  
  
```csharp  
int GetAllAliases(  
   uint          uRequest,   
   IDebugAlias[] ppAliases,   
   out uint      puFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 `uRequest`  
 [in]若要返回的别名的最大数目 (指定传递到的数组的长度`ppAliases`)。  
  
 `ppAliases`  
 [in、 out]使用别名填充数组 (如果这是一个 null 值和`uRequest`为 0，则将返回的别名可返回计数`puFetched`)。  
  
 `puFetched`  
 [out]返回获取的别名数目。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugBinder3](../../../extensibility/debugger/reference/idebugbinder3.md)