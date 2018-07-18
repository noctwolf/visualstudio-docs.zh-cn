---
title: 'Idiaenumsourcefiles:: Item |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSourceFiles::Item method
ms.assetid: 3c19d7ed-0232-4b0e-9b10-f33ed9e0c93b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b1fda746edf51771e7927efd03094f42903141e6
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31458338"
---
# <a name="idiaenumsourcefilesitem"></a>IDiaEnumSourceFiles::Item
通过索引中检索源文件。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Item (   
   DWORD            index,  
   IDiaSourceFile** sourceFile  
);  
```  
  
#### <a name="parameters"></a>参数  
 索引  
 [in]索引的[IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)要检索的对象。 索引是范围 0 到`count`-1，其中`count`返回[idiaenumsourcefiles:: Get_count](../../debugger/debug-interface-access/idiaenumsourcefiles-get-count.md)方法。  
  
 sourceFile  
 [out]返回[IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)表示所需的源文件的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)