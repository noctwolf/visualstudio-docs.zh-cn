---
title: JsSetObjectBeforeCollectCallback 函数 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: ea2cbd94-d8b0-4fa9-a4a1-c75a4e338eaf
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6a472e63afd909ee7bcb74cb2fdd1ae98d6a2938
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24568917"
---
# <a name="jssetobjectbeforecollectcallback-function"></a>JsSetObjectBeforeCollectCallback 函数
设置在对象的垃圾回收之前由运行时调用的回调函数。  
  
## <a name="syntax"></a>语法  
  
```  
STDAPI_(JsErrorCode) JsSetObjectBeforeCollectCallback(  
   _In_ JsRef ref,  
   _In_opt_ void *callbackState,  
   _In_ JsObjectBeforeCollectCallback objectBeforeCollectCallback  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ref`  
 要为其注册回调的对象。  
  
 `callbackState`  
 将传回到回调的用户提供的状态。  
  
 `objectBeforeCollectCallback`  
 要设置的回调函数。 使用 null 清除之前注册的回调。  
  
## <a name="return-value"></a>返回值  
 如果该操作成功，则为代码 `JsNoError` ，否则为失败代码。  
  
## <a name="remarks"></a>备注  
 在当前运行时执行线程上调用回调，因此在回调完成前将阻止执行。  
  
 此 API 仅在“边缘”模式下受到支持。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)