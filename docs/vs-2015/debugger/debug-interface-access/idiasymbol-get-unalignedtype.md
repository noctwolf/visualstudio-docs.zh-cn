---
title: 'Idiasymbol:: Get_unalignedtype |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_unalignedType method
ms.assetid: fdcb38fb-490e-4d15-b4e5-3770043a366c
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2b7deb20f5c5dcacdd31decf2e3892525ef54e62
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "58933204"
---
# <a name="idiasymbolgetunalignedtype"></a>IDiaSymbol::get_unalignedType
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

检索指定用户定义数据类型是否为未对齐的标志。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_unalignedType (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回`TRUE`如果用户定义数据类型为未对齐; 否则为返回`FALSE`。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
