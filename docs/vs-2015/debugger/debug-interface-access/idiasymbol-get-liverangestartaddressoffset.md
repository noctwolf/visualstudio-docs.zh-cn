---
title: IDiaSymbol::get_liveRangeStartAddressOffset |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
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
- IDiaSymbol::get_liveRangeStartAddressOffset
ms.assetid: f5b28914-0a14-4b22-8259-59d7f97ee610
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 07da171ba58c5567a7ea58b68b1834b5ba624e42
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470362"
---
# <a name="idiasymbolgetliverangestartaddressoffset"></a>IDiaSymbol::get_liveRangeStartAddressOffset
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDiaSymbol::get_liveRangeStartAddressOffset](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-liverangestartaddressoffset)。  
  
返回本地符号的范围的起始地址的偏移量的部分。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_liveRangeStartAddressOffset (   
   DWORD* offset  
);  
```  
  
#### <a name="parameters"></a>参数  
 `offset`  
 [out]返回的起始地址范围的偏移量的部分。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
> [!NOTE]
>  返回的错误代码表示符号不具有实时范围信息。  
  
## <a name="remarks"></a>备注  
 通过部分和偏移量而形成的地址是范围的符号无效的开头。  
  
 若要获取的地址部分一部分，请使用[IDiaSymbol::get_liveRangeStartAddressSection](../../debugger/debug-interface-access/idiasymbol-get-liverangestartaddresssection.md)。  
  
## <a name="requirements"></a>要求  
 标头： Dia2.h  
  
 库： diaguids.lib  
  
 DLL: msdia100.dll  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



