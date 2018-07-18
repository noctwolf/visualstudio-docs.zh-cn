---
title: 'Idiasymbol:: Findchildren |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::findChildren method
ms.assetid: 5fe7573a-e48b-428d-9c17-7421b7209246
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 042b02bda59bf064897b0badb24394fc10fb9197
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31465014"
---
# <a name="idiasymbolfindchildren"></a>IDiaSymbol::findChildren
检索的符号的子级。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT findChildren (   
   enum SymTagEnum   symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `symtag`  
 [in]指定要检索的子级的符号标记中定义[SymTagEnum 枚举](../../debugger/debug-interface-access/symtagenum.md)。 设置为`SymTagNull`为要检索的所有子级。  
  
 `name`  
 [in]指定要检索的子级的名称。 设置为`NULL`为要检索的所有子级。  
  
 `compareFlags`  
 [in]指定应用于名称匹配的比较选项。 中的值[NameSearchOptions 枚举](../../debugger/debug-interface-access/namesearchoptions.md)枚举可以单独或组合使用。  
  
 `ppResult`  
 [out]返回[IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)检索包含子符号的列表的对象。  
  
## <a name="return-value"></a>返回值  
 返回`S_OK`如果至少一个子级的符号找，或返回`S_FALSE`如果不发现任何子级; 否则返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法相当于调用[idiasession:: Findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)了该符号后的第一个参数的方法。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 枚举](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasession:: Findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [NameSearchOptions 枚举](../../debugger/debug-interface-access/namesearchoptions.md)