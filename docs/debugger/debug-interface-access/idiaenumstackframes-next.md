---
title: 'Idiaenumstackframes:: Next |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumStackFrames::Next method
ms.assetid: 09378a21-d5e3-4213-b7e2-10f04d85295f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 42d096ce41c5ff9f254e7f44d595159130e43548
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49949844"
---
# <a name="idiaenumstackframesnext"></a>IDiaEnumStackFrames::Next
枚举序列中检索指定的数量的堆栈帧元素。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Next(   
   ULONG             celt,  
   IDiaStackFrame**  rgelt,  
   ULONG*            pceltFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 celt  
 [in]要检索的枚举器中的堆栈帧元素数目。  
  
 rgelt  
 [out]数组，它是与请求填写[IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)对象。  
  
 pceltFetched  
 [out]在提取枚举器返回堆栈数 frame 元素。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`是否存在的堆栈帧。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md)   
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)