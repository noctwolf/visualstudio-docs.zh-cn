---
title: 'Idiasymbol:: Get_databytes |Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
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
- IDiaSymbol::get_dataBytes method
ms.assetid: 5eb37179-20d8-44ae-a72a-405c1b0435c4
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a82f1161fdce536d9a66529eb9faf155c91debbd
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2018
ms.locfileid: "51787648"
---
# <a name="idiasymbolgetdatabytes"></a>IDiaSymbol::get_dataBytes
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索 OEM 符号的数据字节。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_dataBytes (   
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cbData`  
 [in]若要保存的数据缓冲区的大小。  
  
 `pcbData`  
 [out]返回写入字节数，或者，如果`data`参数是`NULL`，返回可用的字节数。  
  
 `data[]`  
 [out]使用的数据字节填充缓冲区。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。  
  
## <a name="requirements"></a>要求  
  
|需求|描述|  
|-----------------|-----------------|  
|标头：|dia2.h|  
|版本:|DIA SDK v7.0|  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



