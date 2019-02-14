---
title: IDiaSession::symsAreEquiv | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::symsAreEquiv method
ms.assetid: 9941d520-e203-46c0-83c3-b3a967f4fc59
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 91a3081cc32eb4286ed7b981dfa2a070dbf4a0ff
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55036688"
---
# <a name="idiasessionsymsareequiv"></a>IDiaSession::symsAreEquiv
检查以查看两个符号是否等效。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT symsAreEquiv (   
   IDiaSymbol* symbolA,  
   IDiaSymbol* symbolB  
);  
```  
  
#### <a name="parameters"></a>参数  
 `symbolA`  
 [in]第一个[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)则比较中使用的对象。  
  
 `symbolB`  
 [in]第二个`IDiaSymbol`则比较中使用的对象。  
  
## <a name="return-value"></a>返回值  
 如果符号为等效，返回`S_OK`; 否则为返回`S_FALSE`，符号不等效。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)