---
title: IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 024ccd78-5867-4ca7-bc26-548758e9ac53
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6c54b1fe2f2826078aa3105a6ac88d4783df2123
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49293821"
---
# <a name="idiasymbolfindsymbolsbyrvaforacceleratorpointertag"></a>IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

提供相应的标记值，此方法返回在指定的相对虚拟地址此存根 （stub） 函数中包含的符号的枚举。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT findSymbolsByRVAForAcceleratorPointerTag (   
   DWORD             tagValue,  
   DWORD             rva,  
   IDiaEnumSymbols** ppResult);  
```  
  
#### <a name="parameters"></a>参数  
 `tagValue`  
 [in]为其找到 pointee 符号记录指针标记值。  
  
 `rva`  
 [in]用于筛选的符号与 pointee 变量和指定的标记值相对应的 rva。  
  
 `ppResult`  
 [out]一个指向`IDiaEnumSymbols`使用结果初始化接口指针。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
## <a name="remarks"></a>备注  
 调用此方法仅对`IDiaSymbol`对应于加速器存根 （stub） 函数的接口。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)



