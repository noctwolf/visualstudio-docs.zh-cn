---
title: BasicType |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- BasicType enumeration
ms.assetid: 19ae53ba-cd6e-47b6-9f94-27ae663ce955
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6a518c3cb800493fdf6c2677a0f09957e2768b0e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47480779"
---
# <a name="basictype"></a>BasicType
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[BasicType](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/basictype)。  
  
指定符号的基本类型。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
enum BasicType {   
   btNoType   = 0,  
   btVoid     = 1,  
   btChar     = 2,  
   btWChar    = 3,  
   btInt      = 6,  
   btUInt     = 7,  
   btFloat    = 8,  
   btBCD      = 9,  
   btBool     = 10,  
   btLong     = 13,  
   btULong    = 14,  
   btCurrency = 25,  
   btDate     = 26,  
   btVariant  = 27,  
   btComplex  = 28,  
   btBit      = 29,  
   btBSTR     = 30,  
   btHresult  = 31  
};  
```  
  
## <a name="elements"></a>元素  
 btNoType  
 不指定任何基本类型。  
  
 btVoid  
 基本类型是`void`。  
  
 btChar  
 基本类型是`char`（C/c + + 类型）。  
  
 btWChar  
 基本类型是宽 (Unicode) 字符 (`WCHAR`)。  
  
 btInt  
 基本类型是`signed int`（C/c + + 类型）。  
  
 btUInt  
 基本类型是`unsigned int`（C/c + + 类型）。  
  
 btFloat  
 基本类型是一个浮点数 (`FLOAT`)。  
  
 btBCD  
 基本类型是二进制编码的十进制数字 (`BCD`)。  
  
 btBool  
 基本类型是一个布尔值 (`BOOL`)。  
  
 btLong  
 基本类型是`long int`（C/c + + 类型）。  
  
 btULong  
 基本类型是`unsigned long int`（C/c + + 类型）。  
  
 btCurrency  
 基本类型是货币。  
  
 btDate  
 基本类型是日期/时间 (`DATE`)。  
  
 btVariant  
 基本类型是变量类型结构 (`VARIANT`)。  
  
 btComplex  
 基本类型是一个复杂的数字。  
  
 btBit  
 一些基本类型。  
  
 btBSTR  
 基本类型是一个基本或二进制字符串 (`BSTR`)。  
  
 btHresult  
 基本类型是`HRESULT`。  
  
## <a name="remarks"></a>备注  
 返回此枚举中的值[idiasymbol:: Get_basetype](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： cvconst.h  
  
## <a name="see-also"></a>请参阅  
 [枚举和结构](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasymbol:: Get_basetype](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)   
 [IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)



