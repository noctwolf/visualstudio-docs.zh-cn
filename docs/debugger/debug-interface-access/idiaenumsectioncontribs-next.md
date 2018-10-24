---
title: 'Idiaenumsectioncontribs:: Next |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSectionContribs::Next method
ms.assetid: a6bb2adb-ee6d-4f3c-ab5b-e89361c8880e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 630914434defea47254597ca0e392379b70a3283
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49818947"
---
# <a name="idiaenumsectioncontribsnext"></a>IDiaEnumSectionContribs::Next
检索指定的数目的枚举序列中的部分发布内容。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Next(   
   ULONG                celt,   
   IDiaSectionContrib** rgelt,  
   ULONG*               pceltFetched  
);  
```  
  
#### <a name="parameters"></a>参数  
 celt  
 [in]要检索的枚举数中的部分发布内容的数。  
  
 rgelt  
 [out]数组，它是用来填充[IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)代表所需的部分发布内容的对象。  
  
 pceltFetched  
 [out]返回中提取的枚举器部分发布内容的数量。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果没有更多的部分发布内容。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)   
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)