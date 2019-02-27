---
title: 'Idiasymbol:: Get_databytes |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_dataBytes method
ms.assetid: 5eb37179-20d8-44ae-a72a-405c1b0435c4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 136ca8c307eb5f0c7a5da2fe7a93c9ac831a4807
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56611833"
---
# <a name="idiasymbolgetdatabytes"></a>IDiaSymbol::get_dataBytes
检索 OEM 符号的数据字节。

## <a name="syntax"></a>语法

```C++
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
- [out]使用的数据字节填充缓冲区。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。

> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。

## <a name="requirements"></a>要求

|需求|说明|
|-----------------|-----------------|
|标头：|dia2.h|
|版本：|DIA SDK v7.0|

## <a name="see-also"></a>请参阅
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)