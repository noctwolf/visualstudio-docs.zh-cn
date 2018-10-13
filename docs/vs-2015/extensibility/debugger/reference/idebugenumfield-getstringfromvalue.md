---
title: IDebugEnumField::GetStringFromValue |Microsoft Docs
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
- IDebugEnumField::GetStringFromValue
helpviewer_keywords:
- IDebugEnumField::GetStringFromValue method
ms.assetid: 5f95fd0c-fdce-497f-9f54-2ad8749494e9
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 54348af99dbade2df126106ab4720434e252a210
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49297708"
---
# <a name="idebugenumfieldgetstringfromvalue"></a>IDebugEnumField::GetStringFromValue
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

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

