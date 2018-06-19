---
title: 'Idiaenumstackframes:: Next |Microsoft 文档'
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
ms.openlocfilehash: 68e84c31cb98cdbbe69e62aa1e572386100277a0
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31458702"
---
# <a name="idiaenumstackframesnext"></a>IDiaEnumStackFrames::Next
从枚举序列中检索指定的数量的堆栈帧元素。  
  
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
 [in]要检索的枚举器中的堆栈帧元素的数目。  
  
 rgelt  
 [out]数组，它是填充了所请求的[IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)对象。  
  
 pceltFetched  
 [out]在提取枚举器返回的数目堆栈框架元素。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果没有更多的堆栈帧。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md)   
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)