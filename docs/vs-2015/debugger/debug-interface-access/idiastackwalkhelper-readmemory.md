---
title: IDiaStackWalkHelper::readMemory |Microsoft Docs
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
- IDiaStackWalkHelper2::readMemory method
ms.assetid: e1eb90aa-49b7-476c-9e70-7e8f08994cbe
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3e110a67f7db5359d9f840f8853307206b84e339
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49201521"
---
# <a name="idiastackwalkhelperreadmemory"></a>IDiaStackWalkHelper::readMemory
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

从可执行文件的映像在内存中读取数据的块。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT readMemory(   
   enum MemoryTypeEnum type,  
   ULONGLONG           va,  
   DWORD               cbData,  
   DWORD*              pcbData,  
   BYTE*               pbData  
);  
```  
  
#### <a name="parameters"></a>参数  
 `type`  
 [in]中的值[MemoryTypeEnum 枚举](../../debugger/debug-interface-access/memorytypeenum.md)枚举，它指定要读取的内存的类型。  
  
 Va  
 [in]从此处开始读取图像中的虚拟地址。  
  
 `cbData`  
 [in]以字节为单位的数据缓冲区的大小。  
  
 `pcbData`  
 [out]返回实际读取的字节数。 如果`pbData`是`NULL`，则表明这是可用的数据的字节总数。  
  
 `pbData`  
 [in、 out]填充读取的内存缓冲区。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [MemoryTypeEnum 枚举](../../debugger/debug-interface-access/memorytypeenum.md)



