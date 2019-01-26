---
title: IDebugExtendedField::IsClosedType |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IsClosedType
- IDebugExtendedField::IsClosedType
ms.assetid: 9136fc57-74ff-4fe4-a6e2-b137cb9d5b08
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6b3c1badda9933c97761d3bf209380ba0c822b7f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55002790"
---
# <a name="idebugextendedfieldisclosedtype"></a>IDebugExtendedField::IsClosedType
确定是否该字段表示封闭的类型。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT IsClosedType(  
   void  
);  
```  
  
```csharp  
int IsClosedType();  
```  
  
## <a name="return-value"></a>返回值  
 如果此字段为关闭的类型，则返回`S_OK`; 否则为返回`S_FALSE`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)