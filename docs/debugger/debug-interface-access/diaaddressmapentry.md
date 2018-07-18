---
title: DiaAddressMapEntry |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DiaAddressMapEntry enumeration
ms.assetid: 5d0ae226-981d-4541-a801-fc4993fe663b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0a29de8f18a9d3123d73210d0e362c2ae2d32641
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "31459800"
---
# <a name="diaaddressmapentry"></a>DiaAddressMapEntry
描述地址映射中的项。  
  
## <a name="syntax"></a>语法  
  
```C++  
struct DiaAddressMapEntry {   
   DWORD rva,  
   DWORD rvaTo  
};  
```  
  
## <a name="elements"></a>元素  
 `rva`  
 A.映像中的相对虚拟地址 (RVA)  
  
 `rvaTo`  
 相对虚拟地址`rva`映像 B.中映射到  
  
## <a name="remarks"></a>备注  
 地址映射提供从一个图像布局 （A） 到另一个 （B） 的转换。 数组`DiaAddressMapEntry`结构按排序`rva`定义地址映射。  
  
 转换一个地址， `addrA`，为地址，一个图像中`addrB`，在图 B 中，执行以下步骤：  
  
1.  搜索的项，映射`e`，最大的排`rva`小于或等于`addrA`。  
  
2.  Set `delta = addrA - e.rva`.  
  
3.  Set `addrB = e.rvaTo + delta`.  
  
 数组`DiaAddressMapEntry`结构传递给[idiaaddressmap:: Set_addressmap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)方法。  
  
## <a name="requirements"></a>要求  
 标头： dia2.h  
  
## <a name="see-also"></a>请参阅  
 [枚举和结构](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaAddressMap::set_addressMap](../../debugger/debug-interface-access/idiaaddressmap-set-addressmap.md)