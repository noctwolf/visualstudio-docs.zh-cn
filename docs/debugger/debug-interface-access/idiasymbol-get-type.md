---
title: IDiaSymbol::get_type | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_type method
ms.assetid: 1c6a4176-dd4e-4c22-8b8f-0e559fc078ba
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a5550ed7551e58140301f6a434d252a534b78228
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227190"
---
# <a name="idiasymbolgettype"></a>IDiaSymbol::get_type
检索表示此符号的类型的符号。

## <a name="syntax"></a>语法

```C++
HRESULT get_type (
    IDiaSymbol** pRetVal
);
```

#### <a name="parameters"></a>参数
`pRetVal`  
[out]返回[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)对象，表示此符号的类型。

## <a name="return-value"></a>返回值
如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。

> [!NOTE]
> 返回值为`S_FALSE`表示该属性不是可用于符号。

## <a name="remarks"></a>备注
若要确定符号的类型，必须调用此方法，并检查生成[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)对象。 请注意，可能具有的类型的符号。 例如，结构的名称具有任何类型，但它可能具有子级的符号 (使用[idiasymbol:: Findchildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)方法来检查这些子级)。

## <a name="example"></a>示例

```C++
IDiaSymbol*         pType;
CComPtr<IDiaSymbol> pBaseType;
if (SUCCEEDED(pType->get_type( &pBaseType ))) {
    BasicType btBaseType;
    if (SUCCEEDED(pBaseType->get_baseType((DWORD *)&btBaseType))) {
        // Do something with basic type.
    }
}
```

## <a name="see-also"></a>请参阅
[IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)  
[IDiaSymbol::get_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)  
[IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)
