---
title: "IDebugClassField::EnumNestedClasses |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugClassField::EnumNestedClasses
helpviewer_keywords:
- IDebugClassField::EnumNestedClasses method
ms.assetid: 2ba5ef0c-395e-4006-9e3c-9b06e1d711d0
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 90a8b7fd2767ca3d7b122a65bf12bf6aed7f17bb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugclassfieldenumnestedclasses"></a>IDebugClassField::EnumNestedClasses
创建此类中嵌套的类的枚举数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumNestedClasses(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumNestedClasses(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppEnum`  
 [out]返回[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)对象表示嵌套类的列表。 如果不有任何嵌套的类，则返回 null 值。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK，则返回 S_FALSE，如果不有任何嵌套的类。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 在枚举每个元素都[IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)描述嵌套的类的对象。  
  
 嵌套的类是在其他类定义的类。 例如:  
  
```  
class RootClass {  
   class NestedClass { }  
};  
```  
  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)枚举将包含一个对象，表示`NestedClass`类。  
  
## <a name="see-also"></a>请参阅  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)