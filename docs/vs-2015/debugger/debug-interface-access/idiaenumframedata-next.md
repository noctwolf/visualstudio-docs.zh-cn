---
title: 'Idiaenumframedata:: Next |Microsoft Docs'
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
- IDiaEnumFrameData::Next method
ms.assetid: 546e2e23-efb2-425a-96a1-808c67c519fb
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 37e9d695c70a3b69357f9d40315ed2359a52fc2f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469770"
---
# <a name="idiaenumframedatanext"></a>IDiaEnumFrameData::Next
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiaenumframedata:: Next](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumframedata-next)。  
  
检索指定的数目的帧枚举序列中的数据元素。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
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
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果没有更多记录。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)



