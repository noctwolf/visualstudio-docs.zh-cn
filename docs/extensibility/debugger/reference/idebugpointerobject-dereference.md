---
title: IDebugPointerObject::Dereference |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: 4cc287887baf2530786b03b591d6c03592055e55
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31113021"
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
 [in]指向一个简单的字节偏移量对象的开头。  
  
 `ppObject`  
 [out]返回[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)对象表示的对象指向，加上偏移，如果有的话。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK;否则，返回错误代码。 如果此对象不指向另一个对象，则返回 E_FAIL。  
  
## <a name="remarks"></a>备注  
 指向的对象可以是基元或例如一个类或结构的更复杂类型。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)