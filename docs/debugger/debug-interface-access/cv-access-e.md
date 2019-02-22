---
title: CV_access_e | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_access_e enumeration
ms.assetid: 33c05d65-abb4-4800-a382-54a3805ea7b0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2b5fa908692167b49c6bb92c892fb143b882d231
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2019
ms.locfileid: "56318571"
---
# <a name="cvaccesse"></a>CV_access_e
指定的成员函数和变量的可见性 （访问级别） 的范围。

## <a name="syntax"></a>语法

```C++
typedef enum CV_access_e {
    CV_private   = 1,
    CV_protected = 2,
    CV_public    = 3
} CV_access_e;
```

## <a name="elements"></a>元素
CV_private  
成员具有私有访问权限。

CV_protected  
访问受保护成员。

CV_public  
成员具有公共访问权限。

## <a name="remarks"></a>备注
`friend`此处访问说明符不包含因为通常由有权访问类的私有和受保护的元素的非成员函数。 使用[idiasymbol:: Get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)方法来使用的查找符号`SymTagFriend`访问。

## <a name="requirements"></a>要求
标头： cvconst.h

## <a name="see-also"></a>请参阅
[枚举和结构](../../debugger/debug-interface-access/enumerations-and-structures.md)  
[IDiaSymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)  
[IDiaSymbol::get_symTag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)
