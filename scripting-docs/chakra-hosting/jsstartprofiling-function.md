---
title: "JsStartProfiling 函数 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsStartProfiling
helpviewer_keywords:
- JsStartProfiling function
ms.assetid: 638da395-42dd-4fc5-b581-819e647e887d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 964e9f26de9cb5000884089da0b404b8d22fdd8d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="jsstartprofiling-function"></a>JsStartProfiling 函数
开始在当前上下文中进行分析。  
  
## <a name="syntax"></a>语法  
  
```  
STDAPI_(JsErrorCode) JsStartProfiling(  
   _In_ IActiveScriptProfilerCallback *callback,  
   _In_ PROFILER_EVENT_MASK eventMask,  
   _In_ unsigned long context  
);  
```  
  
#### <a name="parameters"></a>参数  
 `callback`  
 要使用的分析回调。  
  
 `eventMask`  
 要用于进行回调的分析事件。  
  
 `context`  
 要传递给分析回调的上下文。  
  
## <a name="return-value"></a>返回值  
 如果该操作成功，则为代码 `JsNoError` ，否则为失败代码。  
  
## <a name="remarks"></a>备注  
 需要活动脚本上下文。  
  
 桌面应用支持此 API，但应用商店应用不支持。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)