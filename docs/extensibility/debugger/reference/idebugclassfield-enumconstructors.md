---
title: IDebugClassField::EnumConstructors |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugClassField::EnumConstructors
helpviewer_keywords:
- IDebugClassField::EnumConstructors method
ms.assetid: 66a250b2-75a0-45aa-8d58-40f91cc4bf7b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0a2824eff43103ee2f8c82fba6131325def0c8ea
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49912716"
---
# <a name="idebugclassfieldenumconstructors"></a>IDebugClassField::EnumConstructors
创建此类的构造函数的枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumConstructors(   
   CONSTRUCTOR_ENUM   cMatch,  
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumConstructors(  
   CONSTRUCTOR_ENUM     cMatch,   
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cMatch`  
 [in]中的值[CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md)枚举，用于指定构造函数来枚举的类型。  
  
 `ppEnum`  
 [out]返回[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)对象，表示构造函数的列表。 如果没有的构造函数，则返回 null 值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK 或如果没有的构造函数，则返回 S_FALSE。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 枚举每个元素均[IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)描述构造函数方法的对象。  
  
 通常，构造函数的列表不包括由编译器提供的默认构造函数。  
  
## <a name="see-also"></a>请参阅  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md)