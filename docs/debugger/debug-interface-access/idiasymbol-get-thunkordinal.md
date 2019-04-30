---
title: IDiaSymbol::get_thunkOrdinal | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_thunkOrdinal method
ms.assetid: 4b28d78a-1974-4d8a-8bb7-781bf630f2f4
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6dadfff62502af59652e9113553e13b4942c540f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63401334"
---
# <a name="idiasymbolgetthunkordinal"></a>IDiaSymbol::get_thunkOrdinal
检索一个函数的转换 （thunk） 类型。

## <a name="syntax"></a>语法

```C++
HRESULT get_thunkOrdinal ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>参数
 `pRetVal`

[out]返回一个值从[THUNK_ORDINAL 枚举](../../debugger/debug-interface-access/thunk-ordinal.md)枚举，用于指定函数的转换 （thunk） 类型。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。

> [!NOTE]
> 返回值为`S_FALSE`表示该属性不是可用于符号。

## <a name="remarks"></a>备注
 此属性才有效才形式的符号[SymTagEnum 枚举](../../debugger/debug-interface-access/symtagenum.md)的值`SymTagThunk`。

 "转换 （thunk）"是代码的一种 32 位内存地址空间 （也称为平面地址空间） 和一个 16 位地址空间 （称为分段的地址空间） 之间进行转换。

## <a name="see-also"></a>请参阅
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [THUNK_ORDINAL 枚举](../../debugger/debug-interface-access/thunk-ordinal.md)
- [SymTagEnum 枚举](../../debugger/debug-interface-access/symtagenum.md)