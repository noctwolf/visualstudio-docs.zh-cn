---
title: "IEnumDebugFields::Clone |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IEnumDebugFields::Clone
helpviewer_keywords: IEnumDebugFields::Clone method
ms.assetid: 7ec265a8-696f-45ce-a2a2-0a83e96fee1b
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f9b1379f15ac547aa8ee5fcc1014f3f477c1466c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdebugfieldsclone"></a>IEnumDebugFields::Clone
此方法返回当前枚举作为一个单独的对象的副本。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Clone(  
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int Clone(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppEnum`  
 [out]返回此枚举作为一个单独的对象的副本。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 枚举的副本都在调用此方法时具有与原始相同的状态。 但是，则副本和原始的状态独立，并且可以单独更改。  
  
## <a name="see-also"></a>请参阅  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)