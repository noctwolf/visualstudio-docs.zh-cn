---
title: IDebugObject::IsEqual |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugObject::IsEqual
helpviewer_keywords:
- IDebugObject::IsEqual method
ms.assetid: 4b76e663-ef2e-41ff-9be1-bf26d666a34a
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3ed6ef6736c110864c9ec6e8762475e35e3321cc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469065"
---
# <a name="idebugobjectisequal"></a>IDebugObject::IsEqual
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugObject::IsEqual](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugobject-isequal)。  
  
将与此对象的对象进行比较。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT IsEqual(   
   IDebugObject* pObject,  
   BOOL*         pfIsEqual  
);  
```  
  
```csharp  
int IsEqual(  
   IDebugObject pObject,  
   out int      pfIsEqual  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pObject`  
 [in][IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象，表示要比较的对象。  
  
 `pfIsEqual`  
 [out]返回非零值 (`TRUE`) 的对象的值是相等; 否则为如果返回零 (`FALSE`)。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 通常情况下，此方法可以比较所表示的值的地址`pObject`参数，这[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象; 如果地址相等，则对象可被视为相等。  
  
## <a name="see-also"></a>请参阅  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)

