---
title: IDebugClassField::EnumBaseClasses |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugClassField::EnumBaseClasses
helpviewer_keywords:
- IDebugClassField::EnumBaseClasses method
ms.assetid: 78749674-ef75-46d3-a1f4-ff33afd90e32
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 69c300abde0cd540e34ce351573948d3546e2b3d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483171"
---
# <a name="idebugclassfieldenumbaseclasses"></a>IDebugClassField::EnumBaseClasses
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugClassField::EnumBaseClasses](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugclassfield-enumbaseclasses)。  
  
创建此类的基类的一个枚举器。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
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

