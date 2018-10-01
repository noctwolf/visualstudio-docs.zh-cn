---
title: IDiaPropertyStorage::ReadMultiple |Microsoft Docs
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
- IDiaPropertyStorage::ReadMultiple
ms.assetid: 6ccc9397-ce41-4f72-b261-72ac252cd4a5
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b7acd4d11167adfc086aa462f51324a80a79e0e4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47478855"
---
# <a name="idiapropertystoragereadmultiple"></a>IDiaPropertyStorage::ReadMultiple
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDiaPropertyStorage::ReadMultiple](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiapropertystorage-readmultiple)。  
  
读取指定的属性从当前的属性集。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT ReadMultiple(   
   ULONG          cpspec,  
   PROPSPEC const rgpspec,  
   PROPVARIANT    rgvar  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cpspec`  
 [in]属性中指定的计数`rgpspec`数组。 如果为零，则方法返回没有属性，但的确会返回`S_OK`作为成功代码。  
  
 `rgpspec`  
 [in]要读取的属性数组。 属性 ID 或可选的字符串名称，可以指定属性。 不需要在数组中任何特定顺序中指定属性。 该数组可以包含重复的属性，从而导致重复的属性值返回时的简单属性。 非简单属性应返回访问被拒绝在尝试再次将其打开。 数组可以包含的属性 Id 和字符串 Id 的组合。 此数组必须至少具有`cpspec`属性值的数目。  
  
 `rgvar`  
 [in、 out]一个数组`PROPVARIANT`结构 （Microsoft.VisualStudio.OLE.Interop 命名空间中） 若要使用的每个属性的值进行填充。 该数组必须至少是`cpspec`大小中的元素。 调用方不需要初始化数组中的值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果未找到一个或多个属性。 否则将返回错误代码。  
  
## <a name="remarks"></a>备注  
 如果未找到属性中的相应条目`rgvar`数组包含`VARIANT`类型为`VT_EMPTY`。  
  
## <a name="see-also"></a>请参阅  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)



