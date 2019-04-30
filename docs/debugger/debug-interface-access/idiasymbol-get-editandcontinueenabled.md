---
title: IDiaSymbol::get_editAndContinueEnabled | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_editAndContinueEnabled method
ms.assetid: cd703c64-9ff8-4654-8493-8cde9309cb22
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5fa7521d569267d0ff070b54139fafe3befe0e96
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63401952"
---
# <a name="idiasymbolgeteditandcontinueenabled"></a>IDiaSymbol::get_editAndContinueEnabled
检索一个标志，指示是否编译该模块[/Z7、 /Zi、 /ZI （调试信息格式）](/cpp/build/reference/z7-zi-zi-debug-information-format)编译器开关。

## <a name="syntax"></a>语法

```C++
HRESULT get_editAndContinueEnabled ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>参数
 `pRetVal`

[out]返回`TRUE`编辑并继续已启用在编译; 否则，返回`FALSE`。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。

> [!NOTE]
> 返回值为`S_FALSE`表示该属性不是可用于符号。

## <a name="requirements"></a>要求

|需求|描述|
|-----------------|-----------------|
|标头：|dia2.h|
|版本：|DIA SDK v7.0|

## <a name="see-also"></a>请参阅
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [/Z7、/Zi、/ZI（调试信息格式）](/cpp/build/reference/z7-zi-zi-debug-information-format)