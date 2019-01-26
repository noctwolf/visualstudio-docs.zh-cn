---
title: IDebugEnumField::GetValueFromString |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugEnumField::GetValueFromString
helpviewer_keywords:
- IDebugEnumField::GetValueFromString method
ms.assetid: 1ef8ac5e-a3e0-4078-b876-7f5615aedcbb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fe0947158a93885278b2dbd4191d5ebb169aecee
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54987929"
---
# <a name="idebugenumfieldgetvaluefromstring"></a>IDebugEnumField::GetValueFromString
此方法返回与枚举常量的名称相关联的值。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetValueFromString(  
   LPCOLESTR  pszValue,  
   ULONGLONG* pvalue  
);  
```  
  
```csharp  
int GetValueFromString(  
   string    pszValue,  
   out ulong pValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pszValue`  
 [in]指定要为其获取值的名称的字符串。 请注意，对于 c + +，这是一个宽字符字符串。  
  
 `pValue`  
 [out]返回关联的数字值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`，如果名称不是枚举或错误代码的一部分。  
  
## <a name="remarks"></a>备注  
 此方法是区分大小写。 如果不区分大小写的搜索需要 （例如，在 Visual Basic 名称不区分大小写之类的语言），使用[GetValueFromStringCaseInsensitive](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstringcaseinsensitive.md)。  
  
## <a name="see-also"></a>请参阅  
 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)   
 [GetValueFromStringCaseInsensitive](../../../extensibility/debugger/reference/idebugenumfield-getvaluefromstringcaseinsensitive.md)