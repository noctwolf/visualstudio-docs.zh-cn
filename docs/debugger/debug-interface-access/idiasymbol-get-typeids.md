---
title: 'Idiasymbol:: Get_typeids |Microsoft 文档'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_typeIds method
ms.assetid: 5166e647-fde5-4efe-92bf-77f8ae3fbc9b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6f1ad4aae54096ea2fdcbcac1a68d32fc3b386ad
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31470665"
---
# <a name="idiasymbolgettypeids"></a>IDiaSymbol::get_typeIds
检索有关该股票代码的编译器特定的类型标识符值的数组。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_typeIds (   
   DWORD  cTypeIds,  
   DWORD* pcTypeIds,  
   DWORD  typeIds[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cTypeIds`  
 [in]要保存数据的缓冲区的大小。  
  
 `pcTypeIds`  
 [out]返回的数目`typeIds`编写的或者，如果`typeIds`是`NULL`，然后可用类型标识符的总数。  
  
 `typeIds[]`  
 [out]若要使用的类型标识符填充数组。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值`S_FALSE`意味着属性不是可用于符号。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)