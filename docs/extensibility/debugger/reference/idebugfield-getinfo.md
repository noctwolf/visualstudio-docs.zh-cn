---
title: IDebugField::GetInfo |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugField::GetInfo
helpviewer_keywords:
- IDebugField::GetInfo method
ms.assetid: 7d508200-89ce-400f-a8ea-f28e7610cb2b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d853d63c71e6cc2edb58ec858503f11061ee427b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53823975"
---
# <a name="idebugfieldgetinfo"></a>IDebugField::GetInfo
此方法获取有关字段的可显示信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetInfo(   
   FIELD_INFO_FIELDS dwFields,  
   FIELD_INFO* pFieldInfo  
);  
```  
  
```csharp  
int GetInfo(  
   enum_FIELD_INFO_FIELDS dwFields,  
   FIELD_INFO[] pFieldInfo  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwFields`  
 [in]组合[FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md)选择要显示的信息的常量。 如果该字段表示一个符号，这通常是符号名称和类型。  
  
 `pFieldInfo`  
 [out]返回的信息中提供[FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)结构。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)