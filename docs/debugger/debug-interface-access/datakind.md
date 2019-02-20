---
title: DataKind | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DataKind enumeration
ms.assetid: b64be708-22d6-4360-99e7-8f4e6b196de7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bf8e59bf79355b4e610091ac8662b8d2a01af322
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2019
ms.locfileid: "56318675"
---
# <a name="datakind"></a>DataKind
指示特定的数据值范围。

## <a name="syntax"></a>语法

```C++
enum DataKind {
    DataIsUnknown,
    DataIsLocal,
    DataIsStaticLocal,
    DataIsParam,
    DataIsObjectPtr,
    DataIsFileStatic,
    DataIsGlobal,
    DataIsMember,
    DataIsStaticMember,
    DataIsConstant
};
```

## <a name="elements"></a>元素
DataIsUnknown  
不能确定数据符号。

DataIsLocal  
数据项是一个本地变量。

DataIsStaticLocal  
数据项是一个静态本地变量。

DataIsParam  
数据项是正式的参数。

DataIsObjectPtr  
数据项是一个对象指针 (`this`)。

DataIsFileStatic  
数据项是一个文件范围内的变量。

DataIsGlobal  
数据项是一个全局变量。

DataIsMember  
数据项是一个对象成员变量。

DataIsStaticMember  
数据项是一个类静态变量。

DataIsConstant  
数据项是常量值。

## <a name="remarks"></a>备注
返回此枚举中的值[idiasymbol:: Get_datakind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)方法。

## <a name="requirements"></a>要求
标头： cvconst.h

## <a name="see-also"></a>请参阅
[枚举和结构](../../debugger/debug-interface-access/enumerations-and-structures.md)  
[IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)
