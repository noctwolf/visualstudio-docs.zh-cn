---
title: IDiaSession::findSymbolsByRVAForAcceleratorPointerTag |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a073cc45-0c7b-417e-b5fc-a3b08beccdbc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 49d72f58f57e6779f5f12cc4ed3eba42e6716f63
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54972675"
---
# <a name="idiasessionfindsymbolsbyrvaforacceleratorpointertag"></a>IDiaSession::findSymbolsByRVAForAcceleratorPointerTag
提供相应的标记值，则此方法将返回在指定的父 Accelerator 存根 （stub） 函数在指定的相对虚拟地址中包含的符号的枚举。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT findSymbolsByRVAForAcceleratorPointerTag (   
   IDiaSymbol*           parent,  
   DWORD                 tagValue,  
   DWORD                 rva,  
   IDiaEnumSymbols**     ppResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `parent`  
 [in]`IDiaSymbol` ，对应于要搜索的加速器存根 （stub） 函数。  
  
 `tagValue`  
 [in]指针标记值。  
  
 `rva`  
 [in]相对虚拟地址。  
  
 `ppResult`  
 [out]一个指向`IDiaEnumSymbols`使用结果初始化的接口指针。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 调用此方法仅对`IDiaSymbol`对应于加速器存根 （stub） 函数的接口。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)