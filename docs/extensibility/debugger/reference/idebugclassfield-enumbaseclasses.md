---
title: IDebugClassField::EnumBaseClasses |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugClassField::EnumBaseClasses
helpviewer_keywords:
- IDebugClassField::EnumBaseClasses method
ms.assetid: 78749674-ef75-46d3-a1f4-ff33afd90e32
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3001dab0528a0a21ed11befe75b9d2ef4b314ed1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53986487"
---
# <a name="idebugclassfieldenumbaseclasses"></a>IDebugClassField::EnumBaseClasses
创建此类的基类的一个枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumBaseClasses(   
   IEnumDebugFields** ppEnum  
);  
```  
  
```csharp  
int EnumBaseClasses(  
   out IEnumDebugFields ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppEnum`  
 [out]返回[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)对象，表示基类列表。 如果没有基类，则返回 null 值。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回 S_OK，则返回 S_SH_NO_BASE_CLASSES，如果没有基类 (和`ppEnum`参数设置为 null 值); 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 对大多数远程基类的最直接的 （或派生程度最高的） 基类的顺序指定枚举器对象中的基类。 例如，对于 c + + 类：  
  
```  
class Root { }  
class Level1 : Root { }  
class Level2 : Level1 { }  
class MyClass : Level2 { }  
```  
  
 枚举都将按顺序返回基类`Level2`， `Level1`， `Root`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)