---
title: "IDebugFunctionObject::CreateArrayObject |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugFunctionObject::CreateArrayObject
helpviewer_keywords: IDebugFunctionObject::CreateArrayObject method
ms.assetid: a380e53c-15f1-401f-927f-f366eea789e6
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5dfe24252ce2ce51ff86fa680d94964b86d09365
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfunctionobjectcreatearrayobject"></a>IDebugFunctionObject::CreateArrayObject
创建一个数组对象。 此数组可以包含任一基元或对象实例值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateArrayObject(   
   OBJECT_TYPE    ot,  
   IDebugField*   pClassField,  
   DWORD          dwRank,  
   DWORD          dwDims[],  
   DWORD          dwLowBounds[],  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreateArrayObject(  
   enum_OBJECT_TYPE ot,   
   IDebugField      pClassField,   
   uint             dwRank,   
   uint[]           dwDims,   
   uint[]           dwLowBounds,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ot`  
 [in]指定一个介于[OBJECT_TYPE](../../../extensibility/debugger/reference/object-type.md)枚举，该值指示新的数组对象的类型。  
  
 `pClassField`  
 [in][IDebugField](../../../extensibility/debugger/reference/idebugfield.md)表示对象的类，如果创建实例值的对象的数组对象。 如果创建的基元对象的数组，此参数为 null 值。  
  
 `dwRank`  
 [in]秩或数组的维数。  
  
 `dwDims`  
 [in]每个维度的数组大小。  
  
 `dwLowBounds`  
 [in]每个维度的源 （通常 0 个或 1）。  
  
 `ppObject`  
 [out]返回[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)表示新创建的数组对象。 实际上，这是[IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 调用此方法以创建一个表示由表示的函数的数组参数对象[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)接口。  
  
## <a name="see-also"></a>请参阅  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)