---
title: IDebugGenericFieldDefinition::TypeParamCount |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TypeParamCount
- IDebugGenericFieldDefinition::TypeParamCount
ms.assetid: d41dd5ea-aa25-4bf3-bcfd-e0bf451ead49
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 09a220660c6e2ecd9c64d134b70f65c508f08bb2
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49910766"
---
# <a name="idebuggenericfielddefinitiontypeparamcount"></a>IDebugGenericFieldDefinition::TypeParamCount
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

检索与泛型字段相关联的类型参数的数目。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT TypeParamCount(  
   ULONG32* pcParams  
);  
```  
  
```csharp  
int TypeParamCount(  
   ref uint pcParams  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pcParams`  
 [in、 out]类型参数的数目。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 如果列表\<T >，此方法返回 1，并且，如果列表\<T1，T2 >，此方法返回 2。 如果没有类型参数，此方法将返回 0。  
  
## <a name="see-also"></a>请参阅  
 [IDebugGenericFieldDefinition](../../../extensibility/debugger/reference/idebuggenericfielddefinition.md)

