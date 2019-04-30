---
title: 'Idiasymbol:: Get_upperboundid |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_upperBoundId method
ms.assetid: ddfa1617-bd0f-4187-ba77-a225bab93a95
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2cca35fb1369214672b8740d41f65a2a725517e3
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "63385866"
---
# <a name="idiasymbolgetupperboundid"></a>IDiaSymbol::get_upperBoundId
检索 FORTRAN 数组维度的上限的符号标识符。

## <a name="syntax"></a>语法

```C++
HRESULT get_upperBoundId ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>参数
 `pRetVal`
- [out]返回表示 FORTRAN 数组维度的上限的符号的 ID。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。

> [!NOTE]
> 返回值为`S_FALSE`表示该属性不是可用于符号。

## <a name="remarks"></a>备注
 标识符是唯一的值创建的 DIA SDK，可将标记为唯一的所有符号。

## <a name="see-also"></a>请参阅
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)