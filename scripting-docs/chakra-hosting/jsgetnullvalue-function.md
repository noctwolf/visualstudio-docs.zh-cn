---
title: "JsGetNullValue 函数 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsGetNullValue
helpviewer_keywords:
- JsGetNullValue function
ms.assetid: 132a1496-8dfe-4d3c-a8f8-389f5b0b50d2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d4705f8cbf026002445693907ff70ab03030694
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="jsgetnullvalue-function"></a>JsGetNullValue 函数
获取当前脚本上下文中的 `null` 值。  
  
## <a name="syntax"></a>语法  
  
```  
STDAPI_(JsErrorCode) JsGetNullValue(  
   _Out_ JsValueRef *nullValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `nullValue`  
 `null` 值。  
  
## <a name="return-value"></a>返回值  
 如果该操作成功，则为代码 `JsNoError` ，否则为失败代码。  
  
## <a name="remarks"></a>备注  
 需要活动脚本上下文。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)