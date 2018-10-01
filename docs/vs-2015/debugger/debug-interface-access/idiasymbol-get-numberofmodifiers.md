---
title: IDiaSymbol::get_numberOfModifiers |Microsoft Docs
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
ms.assetid: 61ff7431-1994-4f7e-a182-1817f16f60a9
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 064f536cc1729e93e88943535184a1e270d1346e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47469849"
---
# <a name="idiasymbolgetnumberofmodifiers"></a>IDiaSymbol::get_numberOfModifiers
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDiaSymbol::get_numberOfModifiers](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-numberofmodifiers)。  
  
检索应用于原始类型的修饰符的数目。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT get_numberOfModifiers(   
   DWORD* pRetVal);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]一个指向`DWORD`，它指定应用于原始类型的修饰符的数量。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



