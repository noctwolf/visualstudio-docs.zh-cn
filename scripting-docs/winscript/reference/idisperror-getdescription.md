---
title: IDispError::GetDescription |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispError.GetDescription
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDispError::GetDescription
ms.assetid: 04deaea6-0265-4e34-952e-634edba0e923
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa0c837be9a98829551b9c7820faf154779479e4
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096949"
---
# <a name="idisperrorgetdescription"></a>IDispError::GetDescription
返回此错误的文本说明。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetDescription(  
   BSTR*  pbstrDescription  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrDescription`  
 [out]包含错误的简短说明的字符串。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 在指定的区域设置标识符 (LCID) 传递到的语言中返回的文本`IDispatchEx::InvokeEx`遇到了错误的方法。  
  
> [!NOTE]
>  未实现此方法。  
  
## <a name="see-also"></a>请参阅  
 [IDispError 接口](../../winscript/reference/idisperror-interface.md)   
 [IDispatchEx::InvokeEx](../../winscript/reference/idispatchex-invokeex.md)