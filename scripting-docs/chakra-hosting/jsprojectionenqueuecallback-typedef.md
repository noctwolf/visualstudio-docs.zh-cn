---
title: JsProjectionEnqueueCallback Typedef | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 19c1cefb-a7be-4196-b780-9fe6adf35ba5
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bda4a3a80edac38ab2c3885c2256cdf9d03eb8c1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24568307"
---
# <a name="jsprojectionenqueuecallback-typedef"></a>JsProjectionEnqueueCallback Typedef
当在原始线程以外的线程上完成投影 API 时，JsRT 调用的应用程序回调。  
  
## <a name="syntax"></a>语法  
  
```  
typedef void (CALLBACK *JsProjectionEnqueueCallback)(  
  _In_ JsProjectionCallback jsCallback,  
  _In_ JsProjectionCallbackContext jsContext,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <a name="parameters"></a>参数  
 `jsCallback`  
 要在原始线程上调用的回调。  
  
 `jsContext`  
 应用程序上下文。  
  
 `callbackState`  
 必须传递到 `jsCallback`的 JsRT 上下文。  
  
## <a name="remarks"></a>备注  
 需要调用 JsSetProjectionEnqueueCallback 才能接收回调。  
  
 此 API 仅在“边缘”模式下受到支持。  
  
## <a name="requirements"></a>要求  
 jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)