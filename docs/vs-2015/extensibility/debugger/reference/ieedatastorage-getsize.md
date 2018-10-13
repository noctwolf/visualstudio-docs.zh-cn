---
title: IEEDataStorage::GetSize |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEEDataStorage::GetSize
helpviewer_keywords:
- IEEDataStorage::GetSize
ms.assetid: 33d232c4-1239-4abc-922b-e1bc5b908169
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: fc23ae09bf4cac79aeb9ed0a509b6647d2ccf930
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49187669"
---
# <a name="ieedatastoragegetsize"></a>IEEDataStorage::GetSize
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

返回此对象中包含的字节数。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
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

