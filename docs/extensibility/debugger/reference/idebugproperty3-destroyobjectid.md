---
title: IDebugProperty3::DestroyObjectID |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProperty3::DestroyObjectID
helpviewer_keywords:
- IDebugProperty3::DestroyObjectID
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b0339da5c07741c6db15f2df9db6daad455af699
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53851883"
---
# <a name="idebugproperty3destroyobjectid"></a>IDebugProperty3::DestroyObjectID
销毁，该值指示调用方不再关注来标识唯一中所有其他属性的此属性与此属性相关联的唯一 ID。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DestroyObjectID(  
   void  
);  
```  
  
```csharp  
int DestroyObjectID();  
```  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 如果调试引擎不需要支持的属性的唯一 Id （因为它已跟踪它们唯一内部），则可以只返回`E_NOTIMPL`为此方法。  
  
 通过调用创建唯一 Id [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)方法时调用方想要确保此属性唯一地标识在所有其他属性之间。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)