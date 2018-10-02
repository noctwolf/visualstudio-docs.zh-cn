---
title: 'Idiaenumstackframes:: Next |Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumStackFrames::Next method
ms.assetid: 09378a21-d5e3-4213-b7e2-10f04d85295f
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7b4411d566768b514816fcaaa6386ca91373c159
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47483146"
---
# <a name="idiaenumstackframesnext"></a>IDiaEnumStackFrames::Next
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiaenumstackframes:: Next](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumstackframes-next)。  
  
枚举序列中检索指定的数量的堆栈帧元素。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
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



