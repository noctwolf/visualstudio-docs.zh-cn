---
title: 'Idiaenumsymbols:: Item |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbols::Item method
ms.assetid: 2bd1ec04-e677-4e32-8e32-33334f1eed77
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e90fb2d4ce258560c3588a6dd9b4379c76441773
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="idiaenumsymbolsitem"></a>IDiaEnumSymbols::Item
通过索引中检索一个符号。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Item (   
   DWORD        index,  
   IDiaSymbol** symbol  
);  
```  
  
#### <a name="parameters"></a>参数  
 索引  
 [in]索引的[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)要检索的对象。 索引是范围 0 到`count`-1，其中`count`返回[idiaenumsymbols:: Get_count](../../debugger/debug-interface-access/idiaenumsymbols-get-count.md)方法。  
  
 symbol  
 [out]返回[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)表示所需的符号对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)