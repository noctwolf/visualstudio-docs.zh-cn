---
title: IDiaSymbol::get_isVirtualInheritance |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 72906b92-dd4a-42e3-9b24-b77628fa48c1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: eb0970d7c907821a2ba0578cd5a326688bee2b34
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54922673"
---
# <a name="idiasymbolgetisvirtualinheritance"></a>IDiaSymbol::get_isVirtualInheritance
指定是否`this`指针指向一个具有虚拟继承数据成员。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_isVirtualInheritance(   
   BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]一个指向`BOOL`，它指定是否`this`指针指向一个具有虚拟继承数据成员。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)