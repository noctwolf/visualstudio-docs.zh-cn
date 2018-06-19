---
title: JsDisableRuntimeExecution 函数 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDisableRuntimeExecution
helpviewer_keywords:
- JsDisableRuntimeExecution function
ms.assetid: 4bd4670a-a9da-4f8c-b3fd-1fd366d915c3
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f44545f7c81344a2d22f0083087f77ac8074278c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24568267"
---
# <a name="jsdisableruntimeexecution-function"></a>JsDisableRuntimeExecution 函数
挂起脚本执行，并终止运行时中正在运行的任何脚本。  
  
## <a name="syntax"></a>语法  
  
```  
STDAPI_(JsErrorCode) JsDisableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <a name="parameters"></a>参数  
 `runtime`  
 要挂起的运行时。  
  
## <a name="return-value"></a>返回值  
 如果该操作成功，则为代码 `JsNoError` ，否则为失败代码。  
  
## <a name="remarks"></a>备注  
 调用 `JsEnableRuntimeExecution` 之前，无法调用挂起的运行时。  
  
 不必在运行时处于活动状态的线程上调用此 API。 尽管运行时将进入挂起状态，但正在执行的脚本可能不会立即挂起；而正在运行的脚本将尽快终止并引发不可捕获的异常。  
  
 在已挂起的运行时中挂起执行是一个空操作。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)