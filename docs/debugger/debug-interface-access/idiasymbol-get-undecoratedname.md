---
title: 'Idiasymbol:: Get_undecoratedname |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_undecoratedName method
ms.assetid: e49edf25-a51d-4787-bd5b-2bf5af827c8c
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5f0259a99d292f5852af36a9503d94d6f2eddb1c
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53867873"
---
# <a name="idiasymbolgetundecoratedname"></a>IDiaSymbol::get_undecoratedName
检索有关 c + + 修饰，或链接，名称的未修饰的名称。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_undecoratedName (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回未修饰的名为 c + + 修饰名。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)