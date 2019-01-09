---
title: 'Idiasymbol:: Get_haseha |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_hasEHa method
ms.assetid: cb61dfd9-fe69-461c-8185-288440454864
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 42a075b4447259bfacaf9e31c97f9e51b0b0a730
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53847329"
---
# <a name="idiasymbolgethaseha"></a>IDiaSymbol::get_hasEHa
检索一个标志，指定该函数是否包含异步 （结构化） 异常处理。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_hasEHa(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pFlag`  
 [out]返回`TRUE`如果函数具有任何异步异常处理; 否则，返回`FALSE`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。  
  
## <a name="remarks"></a>备注  
 可以混合使用异步或结构化异常处理与 c + + 样式异常处理，但它需要特定的编译器开关，/EHa，若要启用它。  
  
## <a name="requirements"></a>要求  
  
|需求|说明|  
|-----------------|-----------------|  
|标头：|dia2.h|  
|版本:|DIA SDK v8.0|  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)