---
title: IDebugExpressionContext::GetLanguageInfo |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugExpressionContext.GetLanguageInfo
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugExpressionContext::GetLanguageInfo
ms.assetid: 35e25662-0b2a-4c3f-bce4-f01726bc04a8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e47d25c6545aa906400073685e90774482444182
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093738"
---
# <a name="idebugexpressioncontextgetlanguageinfo"></a>IDebugExpressionContext::GetLanguageInfo
返回拥有此上下文中的语言名称和 GUID。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetLanguageInfo(  
   BSTR*  pbstrLanguageName,  
   GUID*  pLanguageID  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrLanguageName`  
 [out]语言的名称。  
  
 `pLanguageID`  
 [out]语言的唯一 id。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法返回拥有此上下文中的语言名称和 GUID。  
  
## <a name="see-also"></a>请参阅  
 [IDebugExpressionContext 接口](../../winscript/reference/idebugexpressioncontext-interface.md)