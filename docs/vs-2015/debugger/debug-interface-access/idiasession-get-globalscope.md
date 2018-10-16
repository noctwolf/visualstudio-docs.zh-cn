---
title: 'Idiasession:: Get_globalscope |Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
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
- IDiaSession::get_globalScope method
ms.assetid: 75d128a8-3dce-40ed-b392-de3fdda041b7
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9a9586c2278bfdc8e8ec781783a12ff140d1afe
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49269812"
---
# <a name="idiasessiongetglobalscope"></a>IDiaSession::get_globalScope
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索对全局范围内的引用。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_globalScope (   
   IDiaSymbol** pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)表示全局范围内的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [exe](../../debugger/debug-interface-access/exe.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



