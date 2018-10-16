---
title: IDiaSymbol::get_liveRangeStartAddressSection |Microsoft Docs
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
- IDiaSymbol::get_liveRangeStartAddressSection
ms.assetid: 892b80ff-5957-4233-b4d7-6144167be289
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 780901742c0839a65df17e8a499bdec2d3447c58
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49234138"
---
# <a name="idiasymbolgetliverangestartaddresssection"></a>IDiaSymbol::get_liveRangeStartAddressSection
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

返回的部分一部分的本地符号的范围的起始地址。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_liveRangeStartAddressSection (   
   DWORD* section  
);  
```  
  
#### <a name="parameters"></a>参数  
 `section`  
 [out]返回起始地址范围部分的部分。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
> [!NOTE]
>  返回的错误代码表示符号不具有实时范围信息。  
  
## <a name="remarks"></a>备注  
 通过部分和偏移量而形成的地址是范围的符号无效的开头。  
  
 若要获取地址的偏移量的部分，请使用[IDiaSymbol::get_liveRangeStartAddressOffset](../../debugger/debug-interface-access/idiasymbol-get-liverangestartaddressoffset.md)。  
  
## <a name="requirements"></a>要求  
 标头： Dia2.h  
  
 库： diaguids.lib  
  
 DLL: msdia100.dll  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



