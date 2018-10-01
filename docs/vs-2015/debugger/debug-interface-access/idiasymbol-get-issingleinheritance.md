---
title: IDiaSymbol::get_isSingleInheritance |Microsoft Docs
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
ms.assetid: 46cde656-059b-4c20-9476-3ca68ccc9912
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c4c639d896a80c77fcfba974c92ffb49177e987
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471356"
---
# <a name="idiasymbolgetissingleinheritance"></a>IDiaSymbol::get_isSingleInheritance
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDiaSymbol::get_isSingleInheritance](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-issingleinheritance)。  
  
指定是否`this`指针指向单一继承的数据成员。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT get_isSingleInheritance(   
   BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]一个指向`BOOL`，它指定是否`this`指针指向单一继承的数据成员。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



