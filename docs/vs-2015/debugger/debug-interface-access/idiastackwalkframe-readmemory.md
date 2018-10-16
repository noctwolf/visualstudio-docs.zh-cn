---
title: 'Idiastackwalkframe:: Readmemory |Microsoft Docs'
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
- IDiaStackWalkFrame::readMemory method
ms.assetid: 7ab0b525-a5a7-4692-acad-e8c00fa9ab9a
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c5f6758206ced4d4be19552ada3bb4a8ac62e10f
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49300854"
---
# <a name="idiastackwalkframereadmemory"></a>IDiaStackWalkFrame::readMemory
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

从图像中读取内存。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
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
 [in]之一[MemoryTypeEnum 枚举](../../debugger/debug-interface-access/memorytypeenum.md)枚举值，指定要访问的内存的类型。  
  
 `va`  
 [in]要开始读取图像中的虚拟地址位置。  
  
 `cbData`  
 [in]数据缓冲区，以字节为单位的大小。  
  
 `pcbData`  
 [out]返回返回的字节数。 如果`data`是`NULL`，然后`pcbData`包含可用数据的字节总数。  
  
 `data`  
 [out]若要使用从指定的位置的数据填充缓冲区。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)



