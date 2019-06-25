---
title: IDiaSymbol::get_isSdl | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6aa0e116-da75-4643-a4d7-d8e142231e21
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6904fc673462a79578549bcf22c2973a5c10c95c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62836430"
---
# <a name="idiasymbolgetissdl"></a>IDiaSymbol::get_isSdl
指定是否使用 /SDL 选项编译该模块。

## <a name="syntax"></a>语法

```C++
HRESULT get_isSdl(
   BOOL *pRetVal);
```

#### <a name="parameters"></a>参数
 `pRetVal`

[out]一个指向`BOOL`，它指定是否使用 /SDL 选项编译该模块。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。

## <a name="see-also"></a>请参阅
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)