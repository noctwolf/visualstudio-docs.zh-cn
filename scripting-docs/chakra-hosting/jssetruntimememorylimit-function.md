---
title: "JsSetRuntimeMemoryLimit 函数 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryLimit
helpviewer_keywords:
- JsSetRuntimeMemoryLimit function
ms.assetid: 74feb31f-19f6-43e3-b117-0694c59ac593
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 587eb369e6971c7527177624ccf5baf839246cf9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="jssetruntimememorylimit-function"></a>JsSetRuntimeMemoryLimit 函数
设置运行时的当前内存限制。  
  
## <a name="syntax"></a>语法  
  
```  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _In_ size_t memoryLimit  
);  
```  
  
#### <a name="parameters"></a>参数  
 `runtime`  
 将设置其内存限制的运行时。  
  
 `memoryLimit`  
 新的运行时内存限制（以字节为单位），或者 -1 表示无内存限制。  
  
## <a name="return-value"></a>返回值  
 如果该操作成功，则为代码 `JsNoError` ，否则为失败代码。  
  
## <a name="remarks"></a>备注  
 内存限制将导致超过限制的任何操作失败，出现“内存不足”错误。 将运行时的内存限制设置为 -1 表示运行时无内存限制。 新的运行时默认为无内存限制。 如果新的内存限制超出当前使用量，则调用将成功，并且在此运行时中任何将来的分配都将失败，直到运行时的内存使用量低于该限制。  
  
 无论运行时是否在另一个线程上处于活动状态，始终都可以设置运行时的内存限制。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)