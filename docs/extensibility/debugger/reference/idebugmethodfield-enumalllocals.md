---
title: IDebugMethodField::EnumAllLocals |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMethodField::EnumAllLocals
helpviewer_keywords:
- IDebugMethodField::EnumAllLocals method
ms.assetid: 0bc7cc13-2628-4bd8-8c06-4d2aa6755ea8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8c3c13f7252e6f3b662ded697ab267419fd66450
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
ms.locfileid: "31113600"
---
# <a name="idebugmethodfieldenumalllocals"></a>IDebugMethodField::EnumAllLocals
创建的方法，包括那些由编译器内部生成的所有局部变量的枚举数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumAllLocals(   
   IDebugAddress*     pAddress,  
   IEnumDebugFields** ppLocals  
);  
```  
  
```csharp  
int EnumAllLocals(  
   IDebugAddress        pAddress,   
   out IEnumDebugFields ppLocals  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pAddress`  
 [in][IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)对象表示的方法，其指向特定作用域或上下文中的调试地址。  
  
 `ppLocals`  
 [out]返回[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)对象表示的指定范围内的所有局部变量的列表; 否则，返回 null 值，该值指示没有局部变量。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK，则返回 S_FALSE，如果不有任何局部变量。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 枚举只包含给定的调试地址块内定义的变量。 此方法包括任何编译器生成的局部变量。 如果所需的所有源，调用中显式定义的局部变量[EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)方法。  
  
 一种方法可以包含多个作用域的上下文或块。  
  
## <a name="see-also"></a>另请参阅  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)