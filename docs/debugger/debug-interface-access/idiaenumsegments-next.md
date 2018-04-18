---
title: 'Idiaenumsegments:: Next |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments::Next method
ms.assetid: 53f61874-d821-47ab-a1f5-27e982804a6a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 20d3b28131d345d43c74edc93a8bc8441fc7f2d4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idiaenumsegmentsnext"></a>IDiaEnumSegments::Next
检索指定的数量的段中枚举序列。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Next (   
   ULONG         celt,   
   IDiaSegment** rgelt,  
   ULONG*        pceltFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 celt  
 [in]要检索的枚举器中的段的数。  
  
 rgelt  
 [out]数组，它是与所需填充的[IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)表示段的对象。  
  
 pceltFetched  
 [out]在提取枚举器返回的段的数目。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果没有更多的线段。 否则，返回错误代码。  
  
## <a name="see-also"></a>另请参阅  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)