---
title: IDiaEnumSymbolsByAddr::symbolByAddr | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSymbolsByAddr::symbolByAddr method
ms.assetid: 0b6f5a68-8402-4f29-8219-20576fda8166
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c2305c155e0f9790e43514ac4ef68a8e23113e94
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55008343"
---
# <a name="idiaenumsymbolsbyaddrsymbolbyaddr"></a>IDiaEnumSymbolsByAddr::symbolByAddr
枚举数定位通过查找按映像部分数量和偏移量。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT symbolByAddr (   
   DWORD**      isect,  
   DWORD**      offsect,  
   IDiaSymbol** ppsymbol  
);  
```  
  
#### <a name="parameters"></a>参数  
 isect  
 [in]图像部分数。  
  
 offsect  
 [in]在部分中的偏移量。  
  
 ppsymbol  
 [out]返回[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)对象，表示找到的符号。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 `S_OK`。 返回`S_FALSE`如果找不到符号。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)