---
title: IDebugBinder::Bind |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugBinder::Bind
helpviewer_keywords:
- IDebugBinder::Bind method
ms.assetid: 15a11ad7-0fcc-4e80-ae34-8a7dd7bae3c3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 72beca1ede38b310e34edfaabce0ee02e8fb52cc
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53865201"
---
# <a name="idebugbinderbind"></a>IDebugBinder::Bind
此方法获取的内存上下文或对象，其中包含符号的当前值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Bind(   
   IDebugObject*  pContainer,  
   IDebugField*   pField,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int Bind(  
   IDebugObject     pContainer,  
   IDebugField      pField,  
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pContainer`  
 [in][IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)包含引用子`pField`。  
  
 `pField`  
 [in][IDebugField](../../../extensibility/debugger/reference/idebugfield.md)表示该符号。  
  
 `ppObject`  
 [out]返回`IDebugObject`表示实例的符号。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)