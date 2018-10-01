---
title: IDiaStackWalkHelper::readMemory |Microsoft Docs
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
- IDiaStackWalkHelper2::readMemory method
ms.assetid: e1eb90aa-49b7-476c-9e70-7e8f08994cbe
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f8ef913a94dc184339d6c20c97ca8c3f0f3054a4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479319"
---
# <a name="idiastackwalkhelperreadmemory"></a>IDiaStackWalkHelper::readMemory
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDiaStackWalkHelper::readMemory](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkhelper-readmemory)。  
  
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



