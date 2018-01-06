---
title: "IDebugClassField::EnumConstructors |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugClassField::EnumConstructors
helpviewer_keywords: IDebugClassField::EnumConstructors method
ms.assetid: 66a250b2-75a0-45aa-8d58-40f91cc4bf7b
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f0a9e4197f61d01d7d2054055b219b724c04fd0f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugclassfieldenumconstructors"></a>IDebugClassField::EnumConstructors
创建此类的构造函数的枚举数。  
  
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
 [in]取值范围为[CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md)指定的构造函数来枚举类型的枚举。  
  
 `ppEnum`  
 [out]返回[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)对象表示构造函数的列表。 如果没有构造函数，则返回 null 值。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK，或如果没有构造函数将返回 S_FALSE。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 在枚举每个元素都[IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)描述构造函数方法的对象。  
  
 通常，构造函数的列表不包括由编译器提供的默认构造函数。  
  
## <a name="see-also"></a>请参阅  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [CONSTRUCTOR_ENUM](../../../extensibility/debugger/reference/constructor-enum.md)