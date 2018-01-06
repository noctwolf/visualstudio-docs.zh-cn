---
title: "IDebugFunctionObject::CreatePrimitiveObject |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugFunctionObject::CreatePrimitiveObject
helpviewer_keywords: IDebugFunctionObject::CreatePrimitiveObject method
ms.assetid: 6e9dc8b6-b4e1-4abf-b6e0-e885910775bc
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c72dd6d804c37496d2615ccd086ee095c75510d6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugfunctionobjectcreateprimitiveobject"></a>IDebugFunctionObject::CreatePrimitiveObject
创建一个基元数据对象，如简单的整数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreatePrimitiveObject(   
   OBJECT_TYPE    ot,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreatePrimitiveObject(  
   enum_OBJECT_TYPE ot,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ot`  
 [in]取值范围为[OBJECT_TYPE](../../../extensibility/debugger/reference/object-type.md)枚举表示的基元，以便创建的类型。  
  
 `ppObject`  
 [out]返回[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)表示新创建的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，返回，则为 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 调用此方法以创建对象，表示是表示函数的参数的基元对象[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)接口。 例如，如果表达式字符串为"myString(5)"，则此方法将用于创建表示整数 5 的对象。  
  
## <a name="see-also"></a>请参阅  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)