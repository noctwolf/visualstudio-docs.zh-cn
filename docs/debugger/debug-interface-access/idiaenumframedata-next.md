---
title: 'Idiaenumframedata:: Next |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData::Next method
ms.assetid: 546e2e23-efb2-425a-96a1-808c67c519fb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b6a2c4c2a80ea5186b4a3036491bd64a6531d753
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53951558"
---
# <a name="idiaenumframedatanext"></a>IDiaEnumFrameData::Next
检索指定的数目的帧枚举序列中的数据元素。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Next (   
   ULONG           celt,   
   IDiaFrameData** rgelt,  
   ULONG*          pceltFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 celt  
 [in]要检索的枚举器中的帧数据元素数。  
  
 rgelt  
 [out]一个数组[IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)要填充的请求的范围数据元素的对象。  
  
 pceltFetched  
 [out]在提取枚举器返回帧数据元素的数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 `S_OK`。 返回`S_FALSE`如果没有更多记录。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)