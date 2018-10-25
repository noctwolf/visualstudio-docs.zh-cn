---
title: 'Idiatable:: Item |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaTable::Item method
ms.assetid: eae11b26-4807-400c-be25-e85bbc0c6b20
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 476e4d01ed6e092936fc2d9bc7b8e264215e21dc
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49950051"
---
# <a name="idiatableitem"></a>IDiaTable::Item
检索表中指定的项的引用。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Item (   
   DWORD      index,  
   IUnknown** element  
);  
```  
  
#### <a name="parameters"></a>参数  
 `index`  
 [in]在 0 到范围内的表项的索引`count`-1，其中`count`返回的[idiatable:: Get_count](../../debugger/debug-interface-access/idiatable-get-count.md)方法。  
  
 `element`  
 [out]返回`IUnknown`对象，表示指定的表条目。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 表表示的对象的集合。 根据这些对象，可以将元素参数转换为相应的接口。 例如，如果表包含[IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)对象，然后元素参数可强制转换为`IDiaSegment`接口。  
  
 它是一种更常见的方法来调用`QueryInterface`中的方法[IDiaTable](../../debugger/debug-interface-access/idiatable.md)接口的相应枚举器接口，并使用枚举器的特定方法来访问表的内容。 请参阅[IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)有关示例的接口。  
  
## <a name="see-also"></a>请参阅  
 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)   
 [Idiatable:: Get_count](../../debugger/debug-interface-access/idiatable-get-count.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)   
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)