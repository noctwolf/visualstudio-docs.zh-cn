---
title: "Idiaenumdebugstreams:: Next |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumDebugStreams::Next method
ms.assetid: eb8eae5a-be27-45f4-a7bd-6e4ef0652385
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 18f2f06ce6cc1a28ab6f0f77ed18acf6f9177e03
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiaenumdebugstreamsnext"></a>IDiaEnumDebugStreams::Next
检索指定的数目的枚举序列中的调试流。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Next (   
   ULONG                     celt,   
   IDiaEnumDebugStreamData** rgelt,  
   ULONG*                    pceltFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 celt  
 [in]**T**他的要检索的枚举器中的调试流数。  
  
 rgelt  
 [out]返回的数组[IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)对象表示调试流正在检索。  
  
 pceltFetched  
 [out]返回的返回的调试流的数量。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果没有更大的流。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumDebugStreams](../../debugger/debug-interface-access/idiaenumdebugstreams.md)