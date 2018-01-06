---
title: "IDebugPointerField::GetDereferencedField |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugPointerField::GetDereferencedField
helpviewer_keywords: IDebugPointerField::GetDereferencedField method
ms.assetid: 8de988ab-cd79-4287-be72-3c900f2fe407
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f881a7ad6f11b4c916dad8af184d84a434f3e510
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugpointerfieldgetdereferencedfield"></a>IDebugPointerField::GetDereferencedField
此方法返回的此指针对象所指向的对象的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetDereferencedField(  
   IDebugField** ppField  
);  
```  
  
```csharp  
int GetDereferencedField(  
   out IDebugField ppField  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppField`  
 [out]返回[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)描述目标对象的类型。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 例如，如果[IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)对象指向一个整数， [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)此方法返回的类型描述该整数类型。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)