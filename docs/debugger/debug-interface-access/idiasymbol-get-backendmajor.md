---
title: 'Idiasymbol:: Get_backendmajor |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_backEndMajor method
ms.assetid: 900a05dd-c29b-44ad-b46b-f43bda819a66
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cc62c81a1a57b9e9921b6df658d05e8a0a541da0
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2019
ms.locfileid: "64830388"
---
# <a name="idiasymbolgetbackendmajor"></a>IDiaSymbol::get_backEndMajor
检索后端主要编译器的版本号。

## <a name="syntax"></a>语法

```C++
HRESULT get_backEndMajor ( 
   DWORD* pRetVal
);
```

#### <a name="parameters"></a>参数
 `pRetVal`

[out]返回后端主要版本号。 请参阅“备注”。

## <a name="return-value"></a>返回值
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。

> [!NOTE]
> 返回值为`S_FALSE`表示该属性不是可用于符号。

## <a name="remarks"></a>备注
 编译器通常组成两个主要元素： 前端 （分析器），这将其处理为中间格式分析的源代码和一个后端 （代码生成器），后者将中间格式转换到程序集。 不常见的前端具有后端的版本不同。

 前端或后端的版本号三个部分组成：\<主要 >。\<次要 >。\<生成 >，其中\<主要 > 是主版本号，\<次要 > 是的次版本号和\<生成 > 是生成号。 例如，13.10.3077。

## <a name="requirements"></a>要求

|需求|描述|
|-----------------|-----------------|
|标头：|dia2.h|
|版本：|DIA SDK v7.0|

## <a name="see-also"></a>请参阅
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)