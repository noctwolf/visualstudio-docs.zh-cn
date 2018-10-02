---
title: 'Idiaenumtables:: Skip |Microsoft Docs'
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
- IDiaEnumTables::Skip method
ms.assetid: 5c9db956-0654-4f1a-8775-530aa980d8ec
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 49e6e42cf2d24899c54057937b6ded310558298c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482782"
---
# <a name="idiaenumtablesskip"></a>IDiaEnumTables::Skip
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiaenumtables:: Skip](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumtables-skip)。  
  
跳过枚举序列中的表的指定的数目。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 [in]若要跳过枚举序列中的表数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`如果有多个要跳过的表。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)



