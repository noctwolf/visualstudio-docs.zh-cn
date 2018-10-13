---
title: IDebugManagedObject::GetManagedObject |Microsoft Docs
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
- IDebugManagedObject::GetManagedObject
helpviewer_keywords:
- IDebugManagedObject::GetManagedObject method
ms.assetid: 6abe1402-6aad-41e6-8ec1-ae12d5945992
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bd3c5a07c7fc6018c7634cf326517a5fe16a2003
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49204706"
---
# <a name="idebugmanagedobjectgetmanagedobject"></a>IDebugManagedObject::GetManagedObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

返回表示托管的对象的接口。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetManagedObject(   
   IUnknown** ppManagedObject  
);  
```  
  
```cpp#  
int GetManagedObject(  
   out object ppManagedObject  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppManagedObject`  
 [out]返回表示托管的对象的接口。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法返回的接口可以查询由托管类，允许其调用的方法实现任何接口。  
  
## <a name="see-also"></a>请参阅  
 [IDebugManagedObject](../../../extensibility/debugger/reference/idebugmanagedobject.md)

