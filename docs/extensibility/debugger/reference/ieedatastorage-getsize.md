---
title: IEEDataStorage::GetSize |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEEDataStorage::GetSize
helpviewer_keywords:
- IEEDataStorage::GetSize
ms.assetid: 33d232c4-1239-4abc-922b-e1bc5b908169
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 64f78005e4f3f7027cb6621e67cfbe44be4af3a0
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53848741"
---
# <a name="ieedatastoragegetsize"></a>IEEDataStorage::GetSize
返回此对象中包含的字节数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetSize(  
   ULONG* size  
);  
```  
  
```csharp  
int GetSize(  
   out uint size  
);  
```  
  
#### <a name="parameters"></a>参数  
 `size`  
 [out]此对象中包含的字节数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 使用[GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)方法来检索实际数据字节数。  
  
## <a name="see-also"></a>请参阅  
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [GetData](../../../extensibility/debugger/reference/ieedatastorage-getdata.md)