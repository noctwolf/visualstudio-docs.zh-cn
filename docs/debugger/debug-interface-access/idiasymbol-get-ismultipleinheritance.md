---
title: IDiaSymbol::get_isMultipleInheritance |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0aa356a1-5c5c-4ee4-8b48-bae0a2610013
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ab7f0d789527f874f3d3b80b44c58347d1cd84f3
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31465286"
---
# <a name="idiasymbolgetismultipleinheritance"></a>IDiaSymbol::get_isMultipleInheritance
指定是否`this`指针指向一个具有多个继承数据成员。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_isMultipleInheritance(   
   BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]指向的指针`BOOL`，它指定是否`this`指针指向一个具有多个继承数据成员。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)