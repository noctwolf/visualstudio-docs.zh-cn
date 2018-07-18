---
title: JsCreateNamedFunction 函数 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 72f40d06-ab82-4fed-a632-68af6b4126c2
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6a55f3df1d086394a7431b355f037b33e3f4a86c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2017
ms.locfileid: "24567717"
---
# <a name="jscreatenamedfunction-function"></a>JsCreateNamedFunction 函数
创建一个新的具有名称的 JavaScript 函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateNamedFunction(  
   _In_ JsValueRef name,  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### <a name="parameters"></a>参数  
 `name`  
 将用于诊断和串化目的的此函数的名称。  
  
 `nativeFunction`  
 调用函数时要调用的方法。  
  
 `callbackState`  
 将传回到回调的用户提供状态。  
  
 `function`  
 新的函数对象。  
  
## <a name="return-value"></a>返回值  
  
## <a name="remarks"></a>备注  
 需要活动脚本上下文。  
  
 此 API 仅在“边缘”模式下受到支持。  
  
## <a name="requirements"></a>要求  
 **标头：** jsrt.h  
  
## <a name="see-also"></a>另请参阅  
 [引用（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)