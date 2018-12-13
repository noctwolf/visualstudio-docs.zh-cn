---
title: 'Idiasymbol:: Get_rank |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_rank method
ms.assetid: 14cc9c4b-a5ec-414a-b01f-4a142c17b7cc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fc12e9251bd452edc3fdede1a5f7414462162301
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49847690"
---
# <a name="idiasymbolgetrank"></a>IDiaSymbol::get_rank
检索 FORTRAN 多维数组的秩 （维数）。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_rank (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]FORTRAN 多维数组中返回维度的数。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。  
  
## <a name="remarks"></a>备注  
 级别是指其中的数组声明为数组中的维度数量`myarray[1,2,3]`。 此示例具有排名为 3 到 3 个维度。 排名不适用于 c + + 使用每个维度的数组的数组的概念 (即， `myarray[1][2][3]`)。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)