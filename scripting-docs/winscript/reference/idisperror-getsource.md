---
title: IDispError::GetSource |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispError.GetSource
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDispError::GetSource
ms.assetid: 20def54c-a67c-4102-babf-6f0704e5fc5c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 629ecb8427539069bb9e235e733140331875288c
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091814"
---
# <a name="idisperrorgetsource"></a>IDispError::GetSource
返回的类或引发了错误的应用程序的依赖于语言的编程标识符。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetSource(  
   BSTR*  pbstrSource  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrSource`  
 [out]字符串，其中包含窗体中的编程标识符`progname.objectname`。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法用于确定类或应用程序发生异常。 指定在调用时提供的区域设置标识符 (LCID) 的语言中可能会返回的编程标识符。  
  
> [!NOTE]
>  未实现此方法。  
  
## <a name="see-also"></a>请参阅  
 [IDispError 接口](../../winscript/reference/idisperror-interface.md)