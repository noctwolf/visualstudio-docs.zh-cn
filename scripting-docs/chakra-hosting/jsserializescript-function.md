---
title: "JsSerializeScript 函数 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsSerializeScript
helpviewer_keywords: JsSerializeScript function
ms.assetid: ca42c194-e1c1-407d-b542-b9d494e3ac4e
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 92bc6c1de0f2cd43dfe9566413fb64188fd5a382
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
---
# <a name="jsserializescript-function"></a>JsSerializeScript 函数
将已分析的脚本序列化为可重用的缓冲区。  
  
## <a name="syntax"></a>语法  
  
```  
STDAPI_(JsErrorCode) JsSerializeScript(  
   _In_z_ const wchar_t *script,  
   _Out_writes_to_opt_(*bufferSize,  
   *bufferSize) BYTE *buffer,  
   _Inout_ unsigned long *bufferSize  
);  
```  
  
#### <a name="parameters"></a>参数  
 `script`  
 要序列化的脚本。  
  
 `buffer`  
 要在其中放置已序列化的脚本的缓冲区。 可以为 null。  
  
 `bufferSize`  
 进入时，缓冲区大小（以字节为单位）；退出时，保存已序列化脚本所需的缓冲区大小（以字节为单位）。  
  
## <a name="return-value"></a>返回值  
 如果该操作成功，则为代码 `JsNoError` ，否则为失败代码。  
  
## <a name="remarks"></a>备注  
 `JsSerializeScript` 对脚本进行分析，然后以运行时独立格式存储脚本的已分析格式。 然后可在任何运行时中对已序列化的脚本进行反序列化，而无需重新分析脚本。  
  
 需要活动脚本上下文。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)