---
title: JsSetException 函数 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetException
helpviewer_keywords:
- JsSetException function
ms.assetid: c528793a-2e1b-4ee1-bd2e-e63fd547dc40
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5d8fce71f14dedea02e1809fb72281f575f60604
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24568587"
---
# <a name="jssetexception-function"></a>JsSetException 函数
将当前上下文的运行时设置为异常状态。  
  
## <a name="syntax"></a>语法  
  
```  
STDAPI_(JsErrorCode) JsSetException(  
   _In_ JsValueRef exception  
);  
```  
  
#### <a name="parameters"></a>参数  
 `exception`  
 要为当前上下文的运行时设置的 JavaScript 异常。  
  
## <a name="return-value"></a>返回值  
 如果引擎设置为异常状态，则返回 `JsNoError`；否则返回失败代码。  
  
## <a name="remarks"></a>备注  
 如果当前上下文的运行时已处于异常状态，此 API 将返回 `JsErrorInExceptionState`。  
  
 需要活动脚本上下文。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)