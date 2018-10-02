---
title: IDebugField::GetInfo |Microsoft Docs
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
- IDebugField::GetInfo
helpviewer_keywords:
- IDebugField::GetInfo method
ms.assetid: 7d508200-89ce-400f-a8ea-f28e7610cb2b
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 69ff483e9b153c8f95b0ee1a5a5d4334563a31de
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483162"
---
# <a name="idebugfieldgetinfo"></a>IDebugField::GetInfo
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugField::GetInfo](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfield-getinfo)。  
  
此方法获取有关字段的可显示信息。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
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

