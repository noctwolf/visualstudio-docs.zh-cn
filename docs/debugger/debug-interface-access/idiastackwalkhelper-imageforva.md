---
title: 'Idiastackwalkhelper:: Imageforva |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper::imageForVA method
ms.assetid: 8d4edabf-3c01-4fef-8b61-4779f3371067
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 26cb6957edd30d36fbc1a9ebbf982fd3ce91c94a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "54971236"
---
# <a name="idiastackwalkhelperimageforva"></a>IDiaStackWalkHelper::imageForVA
返回在给定的虚拟地址某处的可执行文件的内存空间中的内存中的可执行文件的映像开始。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT imageForVA(  
   ULONGLONG  vaContext,  
   ULONGLONG *pvaImageStart  
);  
```  
  
#### <a name="parameters"></a>参数  
 `vaContext`  
 [in]可执行文件的空间中的某处存在于虚拟地址。  
  
 `pvaImageStart`  
 [out]返回可执行文件的图像的起始虚拟地址。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)