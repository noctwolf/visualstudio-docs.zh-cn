---
title: 'Idiasymbol:: Get_udtkind |Microsoft Docs'
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
helpviewer_keywords:
- IDiaSymbol::get_udtKind method
ms.assetid: 4002f887-aea6-4475-b302-67c57079fe0a
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 04bb2c8226948810285b1afc6c004ca34bc2ef49
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49266053"
---
# <a name="idiasymbolgetudtkind"></a>IDiaSymbol::get_udtKind
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索用户定义类型 (UDT) 的多样性。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_udtKind (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回一个值从[UdtKind 枚举](../../debugger/debug-interface-access/udtkind.md)指定 UDT 类型的枚举： 结构、 类或联合。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [UdtKind 枚举](../../debugger/debug-interface-access/udtkind.md)



