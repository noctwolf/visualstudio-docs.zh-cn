---
title: 'Idiaenumsectioncontribs:: Item |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSectionContribs::Item method
ms.assetid: 63a28f23-0ca0-44a7-b11b-ca0206d642a0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: adbba44ed860c825d1e0baac417bc91e0b33e703
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49901926"
---
# <a name="idiaenumsectioncontribsitem"></a>IDiaEnumSectionContribs::Item
通过索引来检索部分发布内容。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Item (   
   DWORD                index,  
   IDiaSectionContrib** section  
);  
```  
  
#### <a name="parameters"></a>参数  
 索引  
 [in]索引[IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)要检索对象。 索引是 0 到范围内`count`-1，其中`count`返回的[idiaenumsectioncontribs:: Get_count](../../debugger/debug-interface-access/idiaenumsectioncontribs-get-count.md)方法。  
  
 section  
 [out]返回[IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)对象，表示所需的部分中所占比例。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [Idiaenumsectioncontribs:: Get_count](../../debugger/debug-interface-access/idiaenumsectioncontribs-get-count.md)   
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)