---
title: IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 024ccd78-5867-4ca7-bc26-548758e9ac53
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7e42ce2113ed578802074714beac2e317786619b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolfindsymbolsbyrvaforacceleratorpointertag"></a>IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag
给定相应的标记值，则此方法将返回指定的相对虚拟地址在此存根 （stub） 函数中包含的符号的枚举。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT findSymbolsByRVAForAcceleratorPointerTag (   
   DWORD             tagValue,  
   DWORD             rva,  
   IDiaEnumSymbols** ppResult);  
```  
  
#### <a name="parameters"></a>参数  
 `tagValue`  
 [in]为其找到 pointee 符号记录指针标记值。  
  
 `rva`  
 [in]用于筛选到 pointee 变量和指定的标记值相对应的符号 rva。  
  
 `ppResult`  
 [out]指向的指针`IDiaEnumSymbols`结果初始化接口指针。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
## <a name="remarks"></a>备注  
 仅在调用此方法`IDiaSymbol`对应于快捷键存根 （stub） 函数的接口。  
  
## <a name="see-also"></a>另请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)