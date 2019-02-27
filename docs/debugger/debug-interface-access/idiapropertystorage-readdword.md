---
title: IDiaPropertyStorage::ReadDWORD |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadDWORD
ms.assetid: 5f4c034e-a9d3-4560-94b5-ede524741439
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5b4709a218f6586320e96f79ea8a9f423f537c7f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635925"
---
# <a name="idiapropertystoragereaddword"></a>IDiaPropertyStorage::ReadDWORD
读取`DWORD`属性组中的值。

## <a name="syntax"></a>语法

```C++
HRESULT ReadDWORD ( 
   PROPID id,
   DWORD* pValue
);
```

#### <a name="parameters"></a>参数
 `id`

[in]要读取的属性的标识符 (`PROPID`定义为 WTypes.h 中`ULONG`)。

 `pValue`

[out]返回属性值。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则返回错误代码。 返回`E_INVALIDARG`如果该属性的类型不是`DWORD`。

## <a name="remarks"></a>备注
 一个`DWORD`定义由 Windows 为 32 位无符号整数。

## <a name="see-also"></a>请参阅
- [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)