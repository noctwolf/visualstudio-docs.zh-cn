---
title: IDebugEnumField::GetStringFromValue |Microsoft Docs
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
- IDebugEnumField::GetStringFromValue
helpviewer_keywords:
- IDebugEnumField::GetStringFromValue method
ms.assetid: 5f95fd0c-fdce-497f-9f54-2ad8749494e9
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 38dbd88ea8b84c64b277daf5b77970fa127d82fd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471902"
---
# <a name="idebugenumfieldgetstringfromvalue"></a>IDebugEnumField::GetStringFromValue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugEnumField::GetStringFromValue](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugenumfield-getstringfromvalue)。  
  
此方法获取给定其值的枚举常量的名称。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetStringFromValue(  
   ULONGLONG value,  
   BSTR*     pbstrValue  
);  
```  
  
```csharp  
int GetStringFromValue(  
   ulong      value,  
   out string pbstrValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `value`  
 [in]要为其获取枚举的名称的常量值。  
  
 `pbstrValue`  
 [out]返回的枚举常量的名称。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`如果的值没有关联的名称，或返回错误代码。  
  
## <a name="remarks"></a>备注  
 如果有多个相同的值与关联的名称，将返回在枚举中定义的第一个名称。  
  
## <a name="see-also"></a>请参阅  
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)

