---
title: IDebugProperty2::GetReference |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProperty2::GetReference
helpviewer_keywords:
- IDebugProperty2::GetReference method
ms.assetid: 2fa97d9b-c3d7-478e-ba5a-a933f40a0103
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 79cc459248e0a6ac507b357914d94e3fbfbfd8cb
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53857074"
---
# <a name="idebugproperty2getreference"></a>IDebugProperty2::GetReference
返回对该属性的值的引用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetReference(  
   IDebugReference2** ppReference  
);  
```  
  
```csharp  
int GetReference(  
   out IDebugReference2 ppReference  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppRererence`  
 [out]返回[IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)对象，表示对属性的值的引用。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码，通常`E_NOTIMPL`或`E_GETREFERENCE_NO_REFERENCE`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)