---
title: 'Idiaenumlinenumbers:: Item |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers::Item method
ms.assetid: 08efbeaf-22f7-49e9-96a8-bb906dfe4fd8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a00929311c1e8ccaa50d03543f072696bd2bf7f
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31468421"
---
# <a name="idiaenumlinenumbersitem"></a>IDiaEnumLineNumbers::Item
通过索引中检索行号。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Item (   
   DWORD            index,  
   IDiaLineNumber** lineNumber  
);  
```  
  
#### <a name="parameters"></a>参数  
 索引  
 [in]索引的[IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)要检索的对象。 索引是范围 0 到`count`-1，其中`count`返回[idiaenumlinenumbers:: Get_count](../../debugger/debug-interface-access/idiaenumlinenumbers-get-count.md)方法。  
  
 lineNumber  
 [out]返回[IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)对象，表示所需的行号。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)