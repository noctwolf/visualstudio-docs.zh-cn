---
title: IDebugPointerObject::Dereference |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPointerObject::Dereference
helpviewer_keywords:
- IDebugPointerObject::Dereference method
ms.assetid: 196ec2cc-8569-4780-b217-23b24e7f50ca
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d66f49a91d35c90d1422b73dd0f75ee7cbda804b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53830006"
---
# <a name="idebugpointerobjectdereference"></a>IDebugPointerObject::Dereference
获取指向的对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DeReference(   
   DWORD          dwIndex,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int Dereference(  
   uint             dwIndex,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwIndex`  
 [in]指向从该对象的开头的简单的字节偏移量。  
  
 `ppObject`  
 [out]返回[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象表示的对象指向，加上偏移，如果有的话。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。 如果此对象不指向另一个对象，则返回 E_FAIL。  
  
## <a name="remarks"></a>备注  
 指向的对象可以是基元类型或更复杂的类型，例如类或结构。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)