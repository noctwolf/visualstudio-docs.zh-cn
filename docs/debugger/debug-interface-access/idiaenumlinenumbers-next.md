---
title: 'Idiaenumlinenumbers:: Next |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers::Next method
ms.assetid: 363d5b40-1316-4ab8-836f-63637f619e0a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 66abd987e3da4fadaac9d5b2de6664c4ae9e24ac
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56599085"
---
# <a name="idiaenumlinenumbersnext"></a>IDiaEnumLineNumbers::Next
检索指定的数目的枚举序列中的行号。

## <a name="syntax"></a>语法

```C++
HRESULT Next ( 
   ULONG            celt,
   IDiaLineNumber** rgelt,
   ULONG*           pceltFetched
);
```

#### <a name="parameters"></a>参数
 celt

[in]要检索的枚举器中的行号数。

 rgelt

[out]返回的数组[IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)对象表示所需的行号。

 pceltFetched

[out]在提取枚举器返回行号的数。

## <a name="return-value"></a>返回值
 如果成功，则返回 `S_OK`。 返回`S_FALSE`如果没有更多的行号。 否则，返回错误代码。

## <a name="see-also"></a>请参阅
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
- [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)