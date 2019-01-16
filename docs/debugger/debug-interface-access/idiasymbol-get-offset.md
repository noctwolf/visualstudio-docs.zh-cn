---
title: 'Idiasymbol:: Get_offset |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_offset method
ms.assetid: 8292bb08-4dc8-4663-beb4-258f5d5a448d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fd455deb96e423c52743ada25085389b0463bc1a
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53880437"
---
# <a name="idiasymbolgetoffset"></a>IDiaSymbol::get_offset
检索符号位置的偏移的量。 何时使用[LocationType 枚举](../../debugger/debug-interface-access/locationtype.md)是`LocIsRegRel`或`LocIsBitField`。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_offset (   
   LONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回以字节为单位的符号位置的偏移量。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。  
  
## <a name="remarks"></a>备注  
 偏移量是从先前确定的一些已知点。 例如，对于偏移量`LocIsBitField`位置类型通常是从包含类的开头。  
  
## <a name="requirements"></a>要求  
  
|需求|说明|  
|-----------------|-----------------|  
|标头：|dia2.h|  
|版本:|DIA SDK v7.0|  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType 枚举](../../debugger/debug-interface-access/locationtype.md)