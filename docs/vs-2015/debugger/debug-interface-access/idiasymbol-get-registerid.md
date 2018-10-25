---
title: 'Idiasymbol:: Get_registerid |Microsoft Docs'
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
- IDiaSymbol::get_registerId method
ms.assetid: f881e793-eb9e-48dc-a847-dd61d77174fc
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e1ca9b0ba4cdf9a0a95522b4eef5793b9a42d152
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49859689"
---
# <a name="idiasymbolgetregisterid"></a>IDiaSymbol::get_registerId
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索到的位置的注册指示符时[LocationType 枚举](../../debugger/debug-interface-access/locationtype.md)设置为`LocIsEnregistered`。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_registerId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回位置的注册指示符。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。  
  
## <a name="remarks"></a>备注  
 如果符号为相对于寄存器，也就是说，如果符号[LocationType 枚举](../../debugger/debug-interface-access/locationtype.md)设置为`LocIsRegRel`，使用`get_registerId`方法后调用[idiasymbol:: Get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)若要获取从符号所在的位置的寄存器的偏移量的方法。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType 枚举](../../debugger/debug-interface-access/locationtype.md)



