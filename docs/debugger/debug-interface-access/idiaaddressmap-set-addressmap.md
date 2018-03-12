---
title: "Idiaaddressmap:: Set_addressmap |Microsoft 文档"
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
- IDiaAddressMap::set_addressMap method
ms.assetid: 81e82073-089b-43d5-af39-49d7a4907c7a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 681e0bae46497d9b581e89340069937370831777
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idiaaddressmapsetaddressmap"></a>IDiaAddressMap::set_addressMap
提供的地址映射，以支持图像布局翻译。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT set_addressMap (   
   DWORD                     cbData,  
   struct DiaAddressMapEntry data[],  
   BOOL                      imagetoSymbols  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cbData`  
 [in]中的元素数`data`参数。  
  
 `data[]`  
 [in]数组[DiaAddressMapEntry 结构](../../debugger/debug-interface-access/diaaddressmapentry.md)定义转换映射的结构。  
  
 `imagetoSymbols`  
 [in]`TRUE`如果`data`参数 （如所述的调试符号） 定义新的图像布局从映射到原始的布局。 `FALSE`如果`data`是映射到原始的布局中获取的新图像布局。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 通常情况下，DIA 从程序数据库 (.pdb) 文件检索地址转换映射。 如果这些值缺失， [idiaaddressmap:: Set_imageheaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)方法被调用两次，一次与`imagetoSymbols`参数设置为`TRUE`和一次与`imagetoSymbols`参数设置为`FALSE`。 无法使用启用地址映射翻译[idiaaddressmap:: Put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)方法除非提供两个转换映射。  
  
## <a name="see-also"></a>请参阅  
 [DiaAddressMapEntry 结构](../../debugger/debug-interface-access/diaaddressmapentry.md)   
 [IDiaAddressMap](../../debugger/debug-interface-access/idiaaddressmap.md)   
 [Idiaaddressmap:: Put_addressmapenabled](../../debugger/debug-interface-access/idiaaddressmap-put-addressmapenabled.md)   
 [IDiaAddressMap::set_imageHeaders](../../debugger/debug-interface-access/idiaaddressmap-set-imageheaders.md)