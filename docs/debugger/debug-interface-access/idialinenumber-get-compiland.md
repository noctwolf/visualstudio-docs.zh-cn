---
title: 'Idialinenumber:: Get_compiland |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_compiland method
ms.assetid: c476d0b8-c473-47eb-96f5-c4e8f577b1c9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c24c79abb4b907c79c45e6dea5843546e3ce9804
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53851805"
---
# <a name="idialinenumbergetcompiland"></a>IDiaLineNumber::get_compiland
检索对提供的图像的文字的字节将编译单位符号的引用。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_compiland (   
   IDiaSymbol** pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 pRetVal  
 [out]返回[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)提供图像的文字的字节将编译单位的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 `S_OK`。 返回`S_FALSE`如果此属性不受支持。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)