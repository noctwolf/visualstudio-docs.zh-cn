---
title: 'Idiatable:: Get_name |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaTable::get_name method
ms.assetid: f6e9cd07-63cd-48a6-9835-e69c2d0859c5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9c5288b85fef8e292454b8b26cbe9459277b1f40
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53867993"
---
# <a name="idiatablegetname"></a>IDiaTable::get_name
检索表的名称。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_name (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回的表的名称。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)