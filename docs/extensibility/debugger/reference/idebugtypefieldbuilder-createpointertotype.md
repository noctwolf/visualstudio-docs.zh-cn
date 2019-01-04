---
title: IDebugTypeFieldBuilder::CreatePointerToType |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- CreatePointerToType
- IDebugTypeFieldBuilder::CreatePointerToType
ms.assetid: 73966e8a-b643-43e0-9b4e-0aa4b402ebbe
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4445e681320f57a2e8aaf2e39793185b2b963f7a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53938155"
---
# <a name="idebugtypefieldbuildercreatepointertotype"></a>IDebugTypeFieldBuilder::CreatePointerToType
创建为指定类型的指针。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreatePointerToType(  
   IDebugField*  pTypeField,  
   IDebugField** pPtrToTypeField  
);  
```  
  
```csharp  
int CreatePointerToType(  
   IDebugField     pTypeField,  
   out IDebugField pPtrToTypeField  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pTypeField`  
 [in]若要指向的类型。 表示由[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)接口。  
  
 `pPtrToTypeField`  
 [out]返回表示由一个新的指针**IDebugField**对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugTypeFieldBuilder](../../../extensibility/debugger/reference/idebugtypefieldbuilder.md)