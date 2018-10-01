---
title: 'Idiaenumlinenumbers:: Item |Microsoft Docs'
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
- IDiaEnumLineNumbers::Item method
ms.assetid: 08efbeaf-22f7-49e9-96a8-bb906dfe4fd8
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7a74fac7ae3a75d88b70360d36dafe5c4d85cb72
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468938"
---
# <a name="idiaenumlinenumbersitem"></a>IDiaEnumLineNumbers::Item
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiaenumlinenumbers:: Item](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaenumlinenumbers-item)。  
  
通过索引中检索行号。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Item (   
   DWORD            index,  
   IDiaLineNumber** lineNumber  
);  
```  
  
#### <a name="parameters"></a>参数  
 索引  
 [in]索引[IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)要检索对象。 索引是 0 到范围内`count`-1，其中`count`返回的[idiaenumlinenumbers:: Get_count](../../debugger/debug-interface-access/idiaenumlinenumbers-get-count.md)方法。  
  
 行号  
 [out]返回[IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)对象，表示所需的行号。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)



