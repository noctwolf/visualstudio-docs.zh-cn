---
title: IDiaEnumLineNumbers::Item | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumLineNumbers::Item method
ms.assetid: 08efbeaf-22f7-49e9-96a8-bb906dfe4fd8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b25825d4a0c7e3253e1461a163c8211c3e3bdcda
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56607325"
---
# <a name="idiaenumlinenumbersitem"></a>IDiaEnumLineNumbers::Item
通过索引中检索行号。

## <a name="syntax"></a>语法

```C++
HRESULT Item ( 
   DWORD            index,
   IDiaLineNumber** lineNumber
);
```

#### <a name="parameters"></a>参数
 索引

[in]索引[IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)要检索对象。 索引是 0 到范围内`count`-1，其中`count`返回的[idiaenumlinenumbers:: Get_count](../../debugger/debug-interface-access/idiaenumlinenumbers-get-count.md)方法。

 lineNumber

[out]返回[IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)对象，表示所需的行号。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="see-also"></a>请参阅
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
- [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)