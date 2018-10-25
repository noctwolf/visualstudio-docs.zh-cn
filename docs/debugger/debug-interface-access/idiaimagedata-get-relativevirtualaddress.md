---
title: 'Idiaimagedata:: Get_relativevirtualaddress |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaImageData::get_relativeVirtualAddress method
ms.assetid: e6d6deee-dc12-4b38-af15-f917b2d4368e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 032b4db0a69dd1aeec6b312b8506fd29d079cf0c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49935596"
---
# <a name="idiaimagedatagetrelativevirtualaddress"></a>IDiaImageData::get_relativeVirtualAddress
检索虚拟内存中的位置相对于应用程序的模块。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT get_relativeVirtualAddress (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pRetVal`  
 [out]返回该模块的相对虚拟内存偏移量。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaImageData](../../debugger/debug-interface-access/idiaimagedata.md)