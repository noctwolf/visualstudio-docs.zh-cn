---
title: 'Idiasession:: Symsareequiv |Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
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
- IDiaSession::symsAreEquiv method
ms.assetid: 9941d520-e203-46c0-83c3-b3a967f4fc59
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 08b091bfca65c2713f822e50a2bcacb5ac3df587
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482777"
---
# <a name="idiasessionsymsareequiv"></a>IDiaSession::symsAreEquiv
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiasession:: Symsareequiv](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-symsareequiv)。  
  
检查以查看两个符号是否等效。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
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



