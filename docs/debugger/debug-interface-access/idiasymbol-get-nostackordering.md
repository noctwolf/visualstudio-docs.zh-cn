---
title: 'Idiasymbol:: Get_nostackordering |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_noStackOrdering method
ms.assetid: a1753917-705b-4165-9880-d05e91e6dcb4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6b9f570c6ae2e101e319d9789c7e8c7d391008c8
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53963584"
---
# <a name="idiasymbolgetnostackordering"></a>IDiaSymbol::get_noStackOrdering
此函数可检索一个标志，指示是否可以作为堆栈缓冲区检查的一部分实现没有堆栈排序 ([/GS （缓冲区安全检查）](/cpp/build/reference/gs-buffer-security-check)编译器选项)。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_noStackOrdering(  
   BOOL *pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回`TRUE`如果没有堆栈的排序方式可以实现一部分堆栈缓冲区检查; 否则，返回`FALSE`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。  
  
## <a name="requirements"></a>要求  
  
|需求|说明|  
|-----------------|-----------------|  
|标头：|dia2.h|  
|版本:|DIA SDK v8.0|  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [/GS（缓冲区安全检查）](/cpp/build/reference/gs-buffer-security-check)