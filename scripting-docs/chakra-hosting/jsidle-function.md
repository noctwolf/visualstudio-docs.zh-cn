---
title: "JsIdle 函数 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsIdle
helpviewer_keywords: JsIdle function
ms.assetid: 372d1c62-8e19-4886-aa33-364cabc09bba
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ddffd4f37c0e10985a2dbca26558d8a94b21b2f7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="jsidle-function"></a>JsIdle 函数
指示运行时执行它需要的任何空闲处理。  
  
## <a name="syntax"></a>语法  
  
```  
STDAPI_(JsErrorCode) JsIdle(  
   _Out_opt_ unsigned int *nextIdleTick  
);  
```  
  
#### <a name="parameters"></a>参数  
 `nextIdleTick`  
 有更多空闲工作要做时的下一个系统时钟周期。 可以为 null。 如果接下来没有空闲工作要做，则返回时钟周期的最大值。  
  
## <a name="return-value"></a>返回值  
 如果该操作成功，则为代码 `JsNoError` ，否则为失败代码。  
  
## <a name="remarks"></a>备注  
 如果已为当前的运行时启用空闲处理，则调用 `JsIdle` 将告知当前运行时该主机处于空闲状态且运行时可以执行内存清理任务。  
  
 `JsIdle` 也可以返回运行时有更多待执行的空闲工作之前的系统时钟周期数。 在通过此数目的时钟周期之前调用 `JsIdle` 将不执行任何工作。  
  
 需要活动脚本上下文。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)