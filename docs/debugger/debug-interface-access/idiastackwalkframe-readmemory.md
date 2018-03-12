---
title: "Idiastackwalkframe:: Readmemory |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame::readMemory method
ms.assetid: 7ab0b525-a5a7-4692-acad-e8c00fa9ab9a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: cb4680b84ed3507316d628e8323b71e98cf2ccd3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiastackwalkframereadmemory"></a>IDiaStackWalkFrame::readMemory
从映像进行读取内存。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT readMemory (   
   MemoryTypeEnum type,  
   ULONGLONG va,  
   DWORD     cbData,  
   DWORD*    pcbData,  
   BYTE      data[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `type`  
 [in]之一[MemoryTypeEnum 枚举](../../debugger/debug-interface-access/memorytypeenum.md)指定的内存，无法访问类型的枚举值。  
  
 `va`  
 [in]在开始读取的映像中的虚拟地址位置。  
  
 `cbData`  
 [in]数据缓冲区，以字节为单位的大小。  
  
 `pcbData`  
 [out]返回返回的字节的数。 如果`data`是`NULL`，然后`pcbData`包含总的可用数据的字节数。  
  
 `data`  
 [out]是使用从指定位置的数据填充缓冲区。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)