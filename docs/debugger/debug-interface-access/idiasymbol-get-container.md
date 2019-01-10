---
title: 'Idiasymbol:: Get_container |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_container method
ms.assetid: 24e832eb-80b3-484c-a41b-11477ec9de99
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f9b528806091bb0b84e8bd2d10b4594b4bf4d018
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53935874"
---
# <a name="idiasymbolgetcontainer"></a>IDiaSymbol::get_container
此函数检索指向表示父/容器的此符号的符号。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_container(  
   IDiaSymbol **pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回一个指向`IDiaSymbol`包含有关容器的此符号的信息。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回 S_FALSE 或错误代码。  
  
> [!NOTE]
>  返回值为 S_FALSE 表示该属性不是可用于符号。  
  
## <a name="requirements"></a>要求  
  
|需求|说明|  
|-----------------|-----------------|  
|标头：|dia2.h|  
|版本:|DIA SDK v8.0|  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)