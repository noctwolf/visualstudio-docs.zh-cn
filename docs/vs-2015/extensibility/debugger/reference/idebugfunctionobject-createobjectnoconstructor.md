---
title: IDebugFunctionObject::CreateObjectNoConstructor |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugFunctionObject::CreateObjectNoConstructor
helpviewer_keywords:
- IDebugFunctionObject::CreateObjectNoConstructor method
ms.assetid: 4e2bd6d5-f4bd-4c10-a998-3db451c9a0c8
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 13e081de229157aefbc0648699e09a921af5a40a
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51748947"
---
# <a name="idebugfunctionobjectcreateobjectnoconstructor"></a>IDebugFunctionObject::CreateObjectNoConstructor
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

使用没有构造函数创建的对象。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT CreateObjectNoConstructor(   
   IDebugField*   pClassObject,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreateObjectNoConstructor(  
   IDebugField      pClassField,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pClassObject`  
 [in][IDebugField](../../../extensibility/debugger/reference/idebugfield.md)对象，表示要创建的对象的类型。  
  
 `ppObject`  
 [out]返回[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)表示新创建的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 调用此方法以创建一个对象，表示结构或复杂类型 （即不需要构造函数） 函数的参数由表示的实例[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)接口。  
  
 如果对象参数需要一个构造函数，调用[CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md)方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)   
 [CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md)

