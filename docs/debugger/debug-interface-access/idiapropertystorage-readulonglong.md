---
title: "IDiaPropertyStorage::ReadULONGLONG |Microsoft 文档"
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
- IDiaPropertyStorage::ReadULONGLONG
ms.assetid: f80a2e24-5744-4fec-bab0-3ed51aef6e58
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 6468fde1a2822a660a6e15b73c0c5102fcc704bf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiapropertystoragereadulonglong"></a>IDiaPropertyStorage::ReadULONGLONG
读取`ULONGLONG`属性组中的值。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT ReadULONGLONG (   
   PROPID     id,  
   ULONGLONG* pValue  
);  
```  
  
#### <a name="parameters"></a>参数  
 `id`  
 [in]要读取的属性的标识符 (`PROPID`作为 WTypes.h 中定义`ULONG`)。  
  
 `pValue`  
 [out]返回属性值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则返回错误代码。 返回`E_INVALIDARG`如果属性的类型不是`ULONGLONG`。  
  
## <a name="remarks"></a>备注  
 A`ULONGLONG`由 Windows 作为 64 位无符号整数。  
  
## <a name="see-also"></a>请参阅  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)