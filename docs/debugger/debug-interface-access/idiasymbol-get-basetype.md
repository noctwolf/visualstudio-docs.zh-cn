---
title: IDiaSymbol::get_baseType | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_baseType method
ms.assetid: 5c69a241-a8d3-48ed-8b36-27463a196572
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c2844003bf7ec81b256537fe06520dfdff473faa
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227272"
---
# <a name="idiasymbolgetbasetype"></a>IDiaSymbol::get_baseType
检索此符号的基类型<em>。</em>

## <a name="syntax"></a>语法

```C++
HRESULT get_baseType (
    DWORD* pRetVal
);
```

#### <a name="parameters"></a>参数
`pRetVal`  
[out]返回一个值从[BasicType 枚举](../../debugger/debug-interface-access/basictype.md)指定符号的基类型的枚举。

## <a name="return-value"></a>返回值
如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。

> [!NOTE]
> 返回值为`S_FALSE`表示该属性不是可用于符号。

## <a name="remarks"></a>备注
可通过首先获取符号的类型，然后询问的返回类型的基类型确定符号的基本类型。 请注意，某些符号可能不具有基类型，例如，结构名称。

## <a name="example"></a>示例

```C++
IDiaSymbol* pType;
CComPtr<IDiaSymbol> pBaseType;
if (pType->get_type( &pBaseType ) == S_OK)
{
    BasicType btBaseType;
    if (pBaseType->get_baseType((DWORD *)&btBaseType) == S_OK)
    {
        // Do something with basic type.
    }
}
```

## <a name="requirements"></a>要求

|需求|说明​​|
|-----------------|-----------------|
|标头：|dia2.h|
|版本:|DIA SDK v7.0|

## <a name="see-also"></a>请参阅
[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)  
[BasicType 枚举](../../debugger/debug-interface-access/basictype.md)  
[IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)
